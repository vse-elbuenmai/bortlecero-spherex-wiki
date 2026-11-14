# Cómo se llega a los datos

Las puertas de entrada a SPHEREx: búsqueda por posición (SIA), consultas tipo SQL (TAP), Python,
recortes, la copia en S3, qué se puede pedir desde un navegador (CORS) y las herramientas web de IRSA.
Verificado el 13 nov 2026 con pruebas directas a cada servicio. ⏳ El estado de los servicios caduca.

## Buscar qué imágenes cubren un punto: SIA

- **Dirección:** `https://irsa.ipac.caltech.edu/SIA?COLLECTION=…&POS=circle+RA+Dec+radio&RESPONSEFORMAT=…`
  (RA, Dec y radio en grados; formatos `CSV`, `HTML`, `IPAC_TABLE` o VOTable por omisión).
- Es como un endpoint REST de búsqueda: le das un punto y un radio, te devuelve una tabla con una fila
  por imagen.

| `COLLECTION` | Qué devuelve |
|---|---|
| `spherex_dr1` | imágenes DR1 del sondeo de todo el cielo |
| `spherex_qr3` | imágenes QR3 del sondeo de todo el cielo |
| `spherex_dr1_deep` | imágenes DR1 de los campos profundos |
| `spherex_qr3_deep` | imágenes QR3 de los campos profundos |
| `spherex_dr1_cube` | el mosaico FITS del cubo que contiene ese punto |

Para tener todo lo de un punto hay que consultar **DR1 y QR3** (y las `_deep` cerca de los polos
eclípticos). `spherex_qr2` ya devuelve 0 filas.

**Columnas útiles:** `access_url` (el archivo en IRSA), `cloud_access` (JSON con bucket y ruta en S3),
`energy_bandpassname` (`SPHEREx-D1` … `D6`), `em_min`, `em_max` (rango del detector, en metros),
`t_min`, `t_max` (fecha en MJD), `t_exptime`, `obs_id`, `s_region` (el polígono de cielo que cubre),
`obs_release_date`, `obs_collection`, `access_estsize` (kB).

Los archivos de calibración no se encuentran por SIA. Documentación: https://irsa.ipac.caltech.edu/ibe/sia.html

## Consultas tipo SQL: TAP

`https://irsa.ipac.caltech.edu/TAP/sync?QUERY=…&FORMAT=CSV`. El tutorial de recortes de IRSA usa las
tablas `spherex.plane` y `spherex.artifact` (unidas por `planeid`). En el mismo TAP están también
`gaia_dr3_source` (copia de Gaia DR3), `catwise_2020`, `allwise_p3as_psd` y `fp_psc` (2MASS).

## Desde Python

`astroquery.ipac.irsa` es lo que recomienda IRSA: `Irsa.query_sia(pos=…, collection=[…])` e
`Irsa.list_collections(servicetype='SIA', filter='spherex')`. También `pyvo`. Los
[tutoriales oficiales](https://caltech-ipac.github.io/irsa-tutorials/spherex/) lo muestran paso a paso
(licencia BSD-3; se pueden usar citándolos). Ya usan DR1 y QR3 juntos.

| Tutorial | Enlace |
|---|---|
| Introducción a las imágenes espectrales | https://caltech-ipac.github.io/irsa-tutorials/spherex-intro/ |
| Recortes | https://caltech-ipac.github.io/irsa-tutorials/spherex-cutouts/ |
| PSF en los recortes | https://caltech-ipac.github.io/irsa-tutorials/spherex-psf/ |
| Cubos de mosaico | https://caltech-ipac.github.io/irsa-tutorials/spherex-mosaic/ |
| Cubo HiPS de todo el cielo | https://caltech-ipac.github.io/irsa-tutorials/spherex-hipscube/ |
| Herramienta de detección de fuentes | https://caltech-ipac.github.io/irsa-tutorials/spherex-source-discovery-tool-demo/ |

## Recortes

Se añade `?center=RA,Dec&size=grados` a la `access_url` de IRSA. Ejemplo oficial:

`https://irsa.ipac.caltech.edu/ibe/data/spherex/qr3/level2/2026W21_2A/l2b-v27-2026-268/1/level2_2026W21_2A_0001_2D1_spx_l2b-v27-2026-268.fits?center=337.8783221,-5.1891588&size=0.1`

- Parámetros: https://irsa.ipac.caltech.edu/ibe/cutouts.html
- El recorte conserva las seis hojas. IMAGE, FLAGS, VARIANCE y ZODI vienen recortadas; la EPSF viene
  **entera**, por eso pesa ~4 MB aunque los píxeles útiles sean pocos.
- **Sólo existe en IRSA**, no en S3, y **no manda CORS**.
- El Data Explorer también genera un script de descarga de recortes (icono de tijeras → «Generate
  Download Script» → «cutouts»).

## La copia en la nube: AWS S3

- **Bucket** `nasa-irsa-spherex`, región `us-east-1`, público y sin firma. Prefijos `dr1/`, `qr3/`,
  `qr2/`, con las mismas carpetas que IRSA.
- **De IRSA a S3:** se cambia `https://irsa.ipac.caltech.edu/ibe/data/spherex/` por
  `https://nasa-irsa-spherex.s3.us-east-1.amazonaws.com/`.
- **Manda CORS** (`Access-Control-Allow-Origin: *`, `GET` y `HEAD`) y **acepta pedidos por rango**
  (`Range`): se puede leer sólo el encabezado de un archivo de 65 MB.
- **Se deja listar** por prefijo: `…amazonaws.com/?list-type=2&prefix=dr1/level2/&delimiter=/`.
- **Limitación:** las carpetas van por **plan semanal**, no por zona del cielo. S3 no sabe qué imágenes
  cubren un punto; eso lo dice el SIA (que devuelve la ruta de S3 en `cloud_access`).
- Navegar el bucket: https://nasa-irsa-spherex.s3.us-east-1.amazonaws.com/index.html ·
  acceso en la nube: https://irsa.ipac.caltech.edu/cloud_access/#spherex

**Carpetas de calibración** (en `dr1/` y `qr3/`), las que más vienen al caso: `spectral_wcs` (longitud
de onda y ancho por píxel, para ciencia), `spectral_channels` (a qué canal pertenece cada píxel),
`solid_angle_pixel_map` (para pasar de MJy/sr a flujo) y `epsf`. Las demás, en la
[guía de productos](https://caltech-ipac.github.io/spherex-archive-documentation/spherex-data-products/).

## Qué se puede pedir desde una página web (CORS) ⏳

Probado el 13 nov mandando la cabecera `Origin`:

| Servicio | ¿Manda CORS? |
|---|---|
| IRSA SIA (`/SIA`) | **no** |
| IRSA recortes (`/ibe/data/…?center=…`) | **no** |
| IRSA TAP (`/TAP/sync`) | **no** |
| IRSA HiPS (`/data/hips/…`), incluido el cubo de SPHEREx | **sí** |
| S3 `nasa-irsa-spherex`: archivos, rangos y listados | **sí** |
| Gaia en la ESA (`gea.esac.esa.int/tap-server`) | **no** |
| SIMBAD en Harvard (`simbad.cfa.harvard.edu/simbad/sim-tap/sync`) | **sí** |
| Sesame en Harvard y en IDIA | **sí** |
| HiPS de la ESA (`skies.esac.esa.int`) | **sí** |

En limpio: desde el navegador se alcanzan los archivos de S3 (completos o por rangos) y los HiPS. La
búsqueda por posición, los recortes y el TAP de IRSA, y Gaia en la ESA, no se pueden pedir directo desde
una página web.

## Herramientas web de IRSA

Para mirar a mano y para comprobar resultados:

| Herramienta | Para qué | Enlace |
|---|---|---|
| **SPHEREx Data Explorer** | buscar por posición, ver cada imagen con sus banderas y generar recortes | https://irsa.ipac.caltech.edu/applications/spherex |
| **Spectrophotometry Tool** | espectro de un punto por fotometría forzada sobre nivel 2 (es para fuentes puntuales) | https://irsa.ipac.caltech.edu/applications/spherex/tool-spectrophotometry |
| **Mosaic Tool** | mosaicos a la medida por canal (mínimo 6.15″ por píxel) | https://irsa.ipac.caltech.edu/applications/spherex/tool-mosaic |
| Source Discovery Tool | detecta fuentes en una región sin catálogo previo (hoy, un cuaderno de demostración) | tutorial arriba |
| MOST | objetos del sistema solar: calcula la órbita y busca imágenes. **No sirve para estrellas** con movimiento propio | https://irsa.ipac.caltech.edu/applications/MOST |
| IRSA Viewer (Firefly) | abre tablas e imágenes | https://irsa.ipac.caltech.edu/irsaviewer/ |
| Colección de 3I/ATLAS | todas las imágenes del cometa con su posición predicha en cada una | https://irsa.ipac.caltech.edu/data/SPHEREx/docs/comet3iatlas/index.html |

## Fuentes

- Portada de SPHEREx en IRSA: https://irsa.ipac.caltech.edu/Missions/spherex.html
- Guía del archivo, acceso: https://caltech-ipac.github.io/spherex-archive-documentation/spherex-data-access/
- Interfaces para programas de IRSA: https://irsa.ipac.caltech.edu/voapi.html
- Servicio de recortes: https://irsa.ipac.caltech.edu/data/SPHEREx/docs/cutout_tool.html
- Tutoriales de IRSA (BSD-3): https://caltech-ipac.github.io/irsa-tutorials/spherex/
- Pruebas directas de SIA, TAP, recortes, S3 y CORS, 13 nov 2026.
