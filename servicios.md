# Estado de los servicios y respaldos ⏳

Qué servicio responde, cuál está caído y qué usar en su lugar. Probado el 13 nov 2026 (~22:40). El 14 nov
(tarde) se volvió a comprobar: **CDS sigue caído**; IRSA (SIA) y SIMBAD en Harvard responden. Esta
página caduca rápido: si algo no responde, compruébalo en vivo y actualiza la fecha.

| Servicio | Estado | Respaldo que sí respondió |
|---|---|---|
| IRSA: SIA, recortes, TAP, HiPS | ✅ funciona | — |
| AWS S3 `nasa-irsa-spherex` | ✅ funciona, con CORS y pedidos por rango | — |
| Archivo de Gaia de la ESA (TAP) | ✅ funciona | IRSA tiene la tabla `gaia_dr3_source` en su TAP |
| SIMBAD en CDS (`simbad.cds.unistra.fr`) | ❌ caído | `simbad.cfa.harvard.edu` (datos hasta el 14 oct 2026) · `simbad.idia.ac.za` |
| Sesame (nombre → coordenadas) en CDS | ❌ | `https://vizier.cfa.harvard.edu/viz-bin/nph-sesame/…` · `https://vizier.idia.ac.za/viz-bin/nph-sesame/…` (los dos mandan CORS) |
| VizieR en CDS | ❌ | `vizier.cfa.harvard.edu` · `vizier.idia.ac.za` (los catálogos enormes, como Gaia DR3, no están en todos los espejos) |
| Imágenes HiPS de CDS (`alasky`, `alaskybis`) | ❌ | IRSA (`https://irsa.ipac.caltech.edu/data/hips/…`) · ESA (`https://skies.esac.esa.int/…`) · los dos mandan CORS |
| `aladin.js` desde `aladin.cds.unistra.fr/AladinLite/api/v3/latest/` | ❌ 404 | paquete npm `aladin-lite` (por jsDelivr o unpkg) |
| X-Match de CDS, portal de CDS, HiPS de catálogos de CDS | ❌ sin respaldo | cruzar catálogos en local (TOPCAT) o con el TAP de otro archivo |
| WiseView (`byw.tools/wiseview`) | ✅ sólo por **http**; por https rechaza la conexión | — |
| AAVSO VSX (variables) | responde, pero pide verificación de Cloudflare a los programas | catálogo GCVS por el VizieR de Harvard |

## Qué pasó con CDS

Texto de https://cds.unistra.fr/ (leído el 13 y el 14 nov): «CDS is experiencing a cybersecurity
incident within its network of servers located in Strasbourg… access to SIMBAD, VizieR, Aladin image
surveys, X-Match and other services hosted on our main site cds.unistra.fr is currently degraded.» No da
fecha de regreso. CDS publicó su lista de espejos HiPS en
`https://cds.unistra.fr/hips_available_20261109.html`.

## En Python

- `astroquery.simbad`: apuntar a un espejo con `conf.server = "simbad.harvard.edu"` (la página de CDS
  dice que también vale `my_simbad.server = "simbad.harvard.edu"` con astroquery ≥ 0.4.8).
- VizieR: `Vizier(vizier_server="vizier.cfa.harvard.edu")`.

## Capas HiPS de respaldo

Verificadas con CORS `*` el 13 nov:

| Capa | En IRSA | En la ESA |
|---|---|---|
| 2MASS color | `…/data/hips/CDS/2MASS/Color` | `https://skies.esac.esa.int/2MASSColor` |
| AllWISE color | `…/data/hips/CDS/AllWISE/RGB-W4-W2-W1` | `https://skies.esac.esa.int/AllWISEColor` |
| AllWISE W1, W2 | `…/data/hips/CDS/AllWISE/W1`, `/W2` | — |
| DSS2 color | `…/data/hips/CDS/DSS2/color` | `https://skies.esac.esa.int/DSSColor` |
| **SPHEREx DR1, cubo de 102 capas** | `https://irsa.ipac.caltech.edu/data/hips/SPHEREx/spherex_allsky_cube` | — |

`…` = `https://irsa.ipac.caltech.edu`. Lista completa de HiPS de IRSA: https://irsa.ipac.caltech.edu/data/hips/list

## Aladin Lite (npm) ⏳

Al 13 nov: la última estable es **3.8.2** (6 mar 2026); la etiqueta `latest` apunta a **3.9.2-beta**
(15 sep 2026). Licencia: LGPL-3.0 según su repositorio, GPL-3 según su `package.json`. La documentación
de `aladin.cds.unistra.fr` está caída; queda el README de https://github.com/cds-astro/aladin-lite.
Antes de fijar una versión, verificar en npm.

## Fuentes

- Pruebas directas a cada servicio (con cabecera `Origin` para CORS), 13 nov 2026; SIMBAD de CDS, Harvard y SIA de IRSA otra vez el 14 nov.
- Aviso de CDS: https://cds.unistra.fr/
