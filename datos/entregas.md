# Las entregas de datos

Qué entregas de SPHEREx hay, cuáles están vigentes y cómo se combinan. Verificado el 13 nov 2026 contra
las páginas de IRSA, el SIA y el Explanatory Supplement v2.1 («Supp.»). ⏳ Cambia con cada entrega.

| Entrega | Qué contiene | Estado (13 nov) | DOI |
|---|---|---|---|
| **DR1** (anunciada el 12 nov 2026) | todo el primer año (barridos 1 y 2) reprocesado con el pipeline R7, más el **cubo de todo el cielo** en 102 canales | vigente | imágenes [10.26131/IRSA678](https://www.ipac.caltech.edu/doi/10.26131/IRSA678) · cubo [10.26131/IRSA679](https://www.ipac.caltech.edu/doi/10.26131/IRSA679) |
| **QR3** (desde sep 2026) | barridos 3 y 4 (desde el 16 may 2026), también en R7; crece cada semana | vigente | [10.26131/IRSA662](https://www.ipac.caltech.edu/doi/10.26131/IRSA662) |
| QR2 | procesado anterior (pipeline 6.4 a 6.5.6) | fuera de las búsquedas; descarga por URL directa hasta feb 2027 | 10.26131/IRSA652 |
| QR1 | primer procesado | retirada en feb 2026 | 10.26131/IRSA629 |
| DR2 | segundo año reprocesado, con cubos nuevos | después de que termine el año 2 | — |

## Lo que importa

- **DR1 + QR3 forman un solo juego.** Texto de IRSA: «The DR1 spectral images are intended to be used
  together with the QR3 spectral images as a uniformly processed set.» Todo DR1 y QR3 es versión
  `l2b-v27` (pipeline R7). [Página de DR1; SIA]
- **No hace falta tocar QR2.** IRSA avisa: «we advise caution when combining QR2 and QR3 data», porque
  QR3 trae otra calibración de ganancia. Con DR1 ese problema desaparece. [Supp. §2.1]
- Las semanas del 16 may al 19 jul 2026, que salieron primero con la versión vieja, **ya están
  republicadas en R7** dentro de `spherex_qr3`. [SIA, 13 nov]
- **Qué tan frescos son ⏳:** el compromiso es 60 días, pero en la práctica las imágenes aparecen unas
  **4 semanas** después de tomarse. Lo más reciente al 13 nov: observaciones del 2 oct 2026, publicadas el
  29 oct. [columnas `t_min` y `obs_release_date` del SIA]
- El SIA va **un día por detrás** del Data Explorer cuando entra una tanda nueva. [guía del archivo]
- Lo que se entrega son **imágenes espectrales** (nivel 2): una por detector, seis por apuntado. Todavía
  no hay catálogos de fuentes; el de alta confiabilidad está planeado para ago 2027.

## Cómo se cita

Agradecimiento literal de IRSA y DOIs en
[referencias/citas-y-licencias.md](../referencias/citas-y-licencias.md). Se cita el DOI de la entrega que
de verdad se use.

## Fuentes

- Qué es DR1 y cómo citarla: https://irsa.ipac.caltech.edu/data/SPHEREx/docs/overview_dr1.html
- Qué son QR2 y QR3: https://irsa.ipac.caltech.edu/data/SPHEREx/docs/overview_qr.html
- *SPHEREx Explanatory Supplement* v2.1, §2.1: https://irsa.ipac.caltech.edu/data/SPHEREx/docs/SPHEREx_Expsupp.pdf
- Guía del archivo: https://caltech-ipac.github.io/spherex-archive-documentation/
- SIA de IRSA, consultas del 13 nov 2026.
