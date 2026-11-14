# Qué trae un archivo de SPHEREx

Un archivo de nivel 2 por dentro: nombre, hojas, claves del encabezado, canales, banderas, saturación,
astrometría y lo que ensucia la imagen. Verificado el 13 nov 2026 contra el Explanatory Supplement v2.1
(«Supp.») y archivos reales de DR1.

## Lo básico

**Un archivo = una exposición de un detector**: 3.5° × 3.5°, 2,040 × 2,040 píxeles de 6.15″. Los de DR1
medidos pesan **65 MB** (64,952,640 bytes); la documentación dice «~67 MB» y «~70 MB». [S3; Supp. §2.2]

**Nombre:** `level2_[plan]_[salto grande]_[salto chico]D[detector]_spx_l2b-v[versión]-[año]-[día].fits`.

Ejemplo real: `level2_2025W33_2C_0321_1D6_spx_l2b-v27-2026-228.fits`

- plan `2025W33_2C`: semana 33 de 2025, segunda mitad, versión C;
- salto grande `0321`, salto chico `1` (cada salto grande tiene de 1 a 4 chicos);
- `D6`: detector 6, que es la banda 6;
- procesado el día 228 de 2026.

Algunas versiones llevan `l2b_retry-`: pasaron por el reintento de astrometría.

## Las seis hojas

Un FITS es como un libro con varias hojas (HDU): [Supp. §2.2]

| Hoja | Qué es |
|---|---|
| **IMAGE** | brillo en MJy/sr. **No** tiene restada la luz zodiacal ni las líneas de la atmósfera |
| **FLAGS** | avisos por píxel, un bit por aviso (tabla abajo) |
| **VARIANCE** | incertidumbre por píxel, en (MJy/sr)² |
| **ZODI** | modelo de la luz zodiacal, en MJy/sr, para restarlo uno mismo |
| **EPSF** | forma de la estrella por zona del detector: 441 filas (rejilla 21 × 21) en los detectores 1, 2, 4, 5 y 6; 451 (11 × 41) en el 3. El recorte la trae **entera**, por eso un recorte pesa ~4 MB |
| **WCS-WAVE** | qué longitud de onda ve cada píxel. IRSA: «suitable for visualization»; para ciencia se usa el producto Spectral WCS |

## Claves del encabezado que importan

| Clave | Para qué |
|---|---|
| `DATE-BEG`, `DATE-AVG`, `DATE-END`, `MJD-…` | la fecha de la foto, **en UTC** |
| `DETECTOR` | el detector, que es la banda (1 a 6) |
| `SPS_EPA` | 0 o 180: la orientación; con la fecha dice a qué barrido pertenece ([spherex/como-observa.md](../spherex/como-observa.md)) |
| `SPS_ELON`, `SPS_ELAT` | a dónde apuntaba, en coordenadas eclípticas |
| `FINAST` | calidad de la astrometría: 0 = buena · 1 = esquinas corridas un par de píxeles · mayor = **no usar** |
| `WCSRETRY`, `RETRY_WCSMODE`, `WCSSEED`, `WCSSEEDOBS` | si la astrometría salió del reintento y con qué imagen semilla |
| `CTYPE1/2` = `RA---TAN-SIP`, `DEC--TAN-SIP` | proyección tangente con distorsión SIP: el WCS se lee **con SIP** |
| `VERSION` | versión del pipeline |
| `L2.N_TRANSIENT`, `L2.N_HOT`, `L2.N_PERSIST`… | cuántos píxeles llevan cada bandera (nombres según el ejemplo del Supp.; comprobar en un archivo real) |

Los nombres largos usan la convención HIERARCH. [Supp. §2.2 y Apéndice A]

## Los 102 canales

Cada detector se divide en 17 canales. El SIA dice qué **detector** vio un punto, no qué **canal**: la
longitud de onda exacta sale de WCS-WAVE o del producto Spectral WCS.

Centros de las bandas 5 y 6, las únicas donde se ve WISE 0855 (Supp. Tablas 33 y 34, en µm):

- **Banda 5:** 3.834 · 3.867 · 3.901 · 3.936 · 3.970 · 4.005 · 4.041 · 4.076 · 4.112 · 4.148 · 4.184 ·
  4.221 · 4.257 · 4.294 · 4.331 · 4.368 · 4.405
- **Banda 6:** 4.435 · 4.468 · 4.500 · 4.533 · 4.567 · 4.601 · 4.635 · 4.669 · 4.704 · 4.739 · 4.774 ·
  4.808 · 4.843 · 4.879 · 4.915 · 4.952 · 4.989

La lista completa de los 102 está en las Tablas 29 a 34 del Supp. y en las propiedades del HiPS del cubo
([cubo-de-todo-el-cielo.md](cubo-de-todo-el-cielo.md)).

## Banderas (FLAGS)

Nombre y número de bit (Supp. Tabla 16, versión R7; sin cambios en v2.1):

TRANSIENT (0) · OVERFLOW (1) · SUR_ERROR (2) · NONFUNC (6) · DICHROIC (7) · MISSING_DATA (9) · HOT (10)
· COLD (11) · FULLSAMPLE (12) · PHANMISS (14) · NONLINEAR (15) · PERSIST (17) · OUTLIER (19) ·
CROSSTALK (20) · **SOURCE (21)** · GHOST (22) · GHOST_FPA (23) · GHOST_EXT (24) · STREAK (25) ·
**BLOOM (26)** · SNOWBALL (27) · HALO (28) · SATELLITE_HALO (29)

- **SOURCE no es un defecto:** marca píxeles con luz de una fuente conocida. Desde la versión 6.4.0 la
  máscara sigue a la estrella con su movimiento propio. [Supp. Tabla 4]
- **OVERFLOW** se activa a **la mitad** del pozo lleno; si pasa en los primeros segundos, el píxel queda
  en **NaN**. [Supp. Tabla 16]
- Los nombres de los bits vienen también en el encabezado de FLAGS: comprobarlos contra el archivo real.
- Rayos cósmicos: ~1.1 % de píxeles marcados; estelas de satélites: ~0.1 %. [Bock et al. 2026 §V.8]

## Saturación

Inicio de no linealidad (modelo previo al lanzamiento) y umbral de señal alta (S/N 50), en magnitud AB
[Supp. Tabla 25]:

| | B1 | B2 | B3 | B4 | B5 | B6 |
|---|---|---|---|---|---|---|
| Satura a partir de | 11.50 | 11.50 | 11.30 | 11.71 | 10.19 | 9.75 |
| S/N 50 a partir de | 14.74 | 14.79 | 14.61 | 14.85 | 13.46 | 13.17 |

Magnitud más chica = más brillante. Cómo queda cada objeto de prueba frente a esto, en
[objetos/](../objetos/README.md).

## Astrometría (qué tan bien sabe dónde está cada píxel)

- **RMS < 0.3″** contra Gaia y 2MASS (≈ 0.05 px), igual en el centro y en las esquinas. [Supp. §4.2.2]
- La referencia es **Gaia DR3 con el movimiento propio ya aplicado** a la fecha de cada foto.
  [Supp. §3.2.8]
- Fallas: menos de 1 % de las imágenes tras el reintento de R7. [Supp. §3.2.8]
- Distorsión óptica: más de 10 píxeles en las esquinas (el Supp. da «~13 px» y «hasta 15 px»); la
  corrigen los polinomios SIP del encabezado. [Supp. §4.2.2]

## Lo que ensucia una imagen

[Supp. §2.3, §2.4 y §3.1]

- Fantasmas del borde del detector y fantasmas lineales de estrellas muy brillantes.
- El fantasma del divisor de haz: un disco de ~10′, sobre todo entre las bandas 3 y 4.
- Luz parásita de estrellas a ~8° del centro (bandas 2 a 6) y luz de la Luna en los bordes.
- Rayos cósmicos, «bolas de nieve» y estelas de satélites.
- Diafonía: una imagen negativa de la fuente brillante 32 filas más allá.
- **Líneas de la atmósfera, que no se restan:** helio a 1.083 µm (decenas de veces la luz zodiacal),
  auroras (bandas 1 y 2) y otras en 0.78, 0.84, 0.93, 1.13, 1.81, 2.63, 2.75, 4.03 y 4.64 µm.
- Resplandor de la nave a ~2.9 µm (banda 4) y ~4.5 µm (bandas 5 y 6).
- La máscara SOURCE depende de la magnitud del catálogo: si está mal, queda chica o grande.
- Hay una lista pública de imágenes muy contaminadas: https://spherex.caltech.edu/page/anomalyimages

## Fuentes

- *SPHEREx Explanatory Supplement* v2.1 (10 nov 2026): https://irsa.ipac.caltech.edu/data/SPHEREx/docs/SPHEREx_Expsupp.pdf
- Guía de productos del archivo: https://caltech-ipac.github.io/spherex-archive-documentation/spherex-data-products/
- Bock et al. 2026, ApJ 999, 139 — https://arxiv.org/abs/2511.02985
- Tamaño medido con la cabecera `Content-Range` de S3, 13 nov 2026.
