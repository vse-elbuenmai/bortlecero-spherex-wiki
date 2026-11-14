# SPHEREx: la misión

La ficha de la misión: qué es, cómo es la nave y la cámara, dónde está, para qué se hizo y su
cronología. Armada el 9 nov 2026 con fuentes oficiales (NASA, JPL, Caltech, IPAC/IRSA) y los papers del
equipo de la misión; revisada el 13 nov contra el Explanatory Supplement **v2.1** (10 nov 2026). Las
siglas entre corchetes remiten a las [fuentes](#fuentes).

## En una frase

SPHEREx es un telescopio infrarrojo pequeño (20 cm) de la NASA que **fotografía el cielo entero cada
seis meses en 102 colores**. Con eso arma un espectro de baja resolución de cada estrella y galaxia del
cielo: el primer mapa espectral de todo el cielo en el infrarrojo cercano. [By the Numbers; JPL dic 2025]

- **Nombre:** *Spectro-Photometer for the History of the Universe, Epoch of Reionization and Ices
  Explorer.*
- **Tipo:** misión Explorer de clase media (MIDEX) de la NASA. [JPL Management]
- **Estado ⏳:** activa, en su segundo año de sondeo (barridos 3 y 4 desde el ~16 may 2026).

Analogía: WISE fotografió el cielo en 4 colores; SPHEREx lo hace en 102. Es pasar de una foto con 4
filtros a un catálogo donde cada artículo trae su ficha completa.

## La nave

| Dato | Valor | Fuente |
|---|---|---|
| Tamaño | 2.6 m de alto × 3.2 m de ancho y fondo | JPL Quick Facts |
| Masa | 502 kg | JPL Quick Facts |
| Energía | un panel solar de 2.67 × 1.02 m, ~750 W | JPL Quick Facts |
| Constructor | BAE Systems (antes Ball Aerospace), Boulder | JPL Management |
| Cómo apunta | gira la nave entera con ruedas de reacción, sin propulsores | Caltech, 1 may 2025 |
| Partes móviles | ninguna, salvo la tapa del telescopio (expulsada una vez) | Caltech, Instrument |
| Costo | ~US$488 millones en todo su ciclo | JPL Quick Facts |

## El telescopio y la cámara

| Dato | Valor | Fuente |
|---|---|---|
| Telescopio | tres espejos de aluminio, apertura efectiva **20 cm** | Caltech, Instrument |
| Campo de visión | 2 × (3.5° × 11.3°), separados por un divisor dicroico; cada detector ve **3.5° × 3.5°** | Instrument; Survey |
| Detectores | **6 detectores H2RG** de 2K × 2K: 3 hasta 2.5 µm (SWIR) y 3 hasta 5.3 µm (MWIR) | Instrument |
| Imagen útil | 2,040 × 2,040 píxeles por detector | IRSA |
| Píxel | **6.15″** (se redondea a 6.2″) | Bock et al. 2026; Supp. |
| Filtros | 6 filtros lineales variables (**LVF**), uno por detector: el color cambia de un borde al otro | Instrument |
| Colores | **102 = 6 detectores × 17 canales** | JPL dic 2025 |
| Rango | 0.75 a 5.0 µm | IRSA |
| Nitidez (PSF) | SWIR: mejor que 3″ en casi todo el campo (hasta 6″ en esquinas de la banda 3); MWIR: hasta 5.5″ | Bock et al. 2026 §IV.3.2 |

**Las seis bandas** (valores de IRSA, medidos en vuelo):

| Banda = detector | Rango (µm) | Resolución R | Lado |
|---|---|---|---|
| 1 | 0.75 – 1.09 | 39 | SWIR |
| 2 | 1.10 – 1.62 | 41 | SWIR |
| 3 | 1.63 – 2.41 | 41 | SWIR |
| 4 | 2.42 – 3.82 | 35 | MWIR |
| 5 | 3.83 – 4.41 | 112 | MWIR |
| 6 | 4.42 – 5.00 | 128 | MWIR |

R ≈ 40 quiere decir que distingue colores separados por ~1/40 de su longitud de onda: un espectro «a
grandes rasgos», suficiente para ver agua, metano o CO₂. Las bandas 5 y 6 tienen más resolución porque
ahí están las huellas de los hielos. [IRSA; Survey]

## El frío

Se enfría de forma **pasiva**, sin electricidad ni refrigerante: tres escudos cónicos anidados y
radiadores. En vuelo: escudos a 290, 150 y 90 K; detectores MWIR a **45 K** y SWIR a **62 K**.
[Instrument; Bock et al. 2026 §V] Hace falta tanto frío porque el calor del propio telescopio brilla en
infrarrojo y taparía la señal.

Como no gasta refrigerante, su frío no se agota (WISE sí lo perdió en su primer año). Sin propulsión, la
órbita decae por el roce con la atmósfera; la reentrada se espera dentro de los 25 años siguientes al fin
de las operaciones científicas. [Supp. §1.2]

## Cómo toma las fotos

| Dato | Valor | Fuente |
|---|---|---|
| Exposición | **113.58 s** según el instrumento y el SIA (`t_exptime`); el paper de la misión dice 116.9 s | Supp. Tabla 2; Bock et al. 2026 §IV.1 |
| Por día | ~600 exposiciones × 6 detectores ≈ **3,600 imágenes** | Caltech, 1 may 2025 |
| Apuntado | 0.15″ rms de estabilidad | Bock et al. 2026 §V.3 |
| Datos | ~20 GB al día | Bock et al. 2026 §IV.5 |
| Profundidad, tras 4 barridos | 5σ: AB 19.5–19.9 (0.75–3.8 µm) y AB 17.8–18.8 (3.8–5.0 µm) | Bock et al. 2026 |

El paper de la misión dice que el desempeño **supera los requisitos** en temperatura, PSF, apuntado y
sensibilidad. [Bock et al. 2026; Korngut et al. 2026]

## Dónde está

Órbita baja, polar y **heliosíncrona** sobre la línea día-noche, a ~650 km, con periodo de ~98 min
(~14.5 vueltas al día). Siempre mira a más de 91–93.5° del Sol. [By the Numbers; Bock et al. 2026
Tabla 1 y §IV.2] Cómo eso se convierte en un barrido del cielo está en
[como-observa.md](como-observa.md).

## Para qué se hizo

| Meta | En simple |
|---|---|
| **Origen del universo** | probar la inflación midiendo en 3D dónde están más de 450 millones de galaxias |
| **Historia de las galaxias** | cuánta luz han emitido todas las galaxias, en los dos campos profundos |
| **Origen del agua** | cuánta agua y otros hielos hay en las nubes donde nacen estrellas y planetas |

[spherex.caltech.edu; JPL dic 2025] De regalo: más de 100 millones de estrellas de la Vía Láctea y
espectros de unos 100,000 asteroides (estimación previa al lanzamiento). [Bock et al. 2026 §II.5]

**Ver cosas que se mueven es un uso secundario.** El píxel de 6.15″ se eligió para cubrir todo el
cielo rápido (6.15″ × 2,040 ≈ 3.5° por foto), no para el detalle fino. Por eso, en el reto, el
movimiento de una estrella entre pasadas es menor que un píxel ([trampas.md](../trampas.md)).

## Cronología

| Fecha | Hito |
|---|---|
| 13 feb 2019 | La NASA la selecciona como su siguiente Explorer mediana |
| **12 mar 2025, 03:10 UTC** (11 mar en California) | Lanzamiento en un Falcon 9 desde Vandenberg, junto con PUNCH |
| 27 mar 2025 | Primeras exposiciones |
| **1 may 2025** | Empieza el sondeo científico |
| jul 2025 | Primera entrega pública (QR1) |
| ago 2025 | Observa el cometa interestelar 3I/ATLAS |
| **18 dic 2025** | Primer mapa de todo el cielo en 102 colores |
| ~16 may 2026 | Empiezan los barridos 3 y 4 |
| 1 jul 2026 | Preprint con espectros de 37 enanas marrones, incluida WISE 0855 |
| sep 2026 | Datos QR3, con nueva calibración de ganancia |
| 28 oct 2026 | La NASA selecciona The Rogue Worlds Project (ciencia ciudadana sobre SPHEREx) |
| **12 nov 2026** | Sale **DR1** en IRSA, con el cubo de todo el cielo |

**Lo que viene ⏳** (planeado): fin del sondeo principal hacia jun 2027 (25 meses desde el 1 may 2025);
catálogo final en ene 2028, con espectros resueltos en el tiempo de estrellas brillantes. Extensión de la
misión: no se encontró ninguna decisión oficial. [spherex.caltech.edu; Supp. §1.1; NASA Senior Review 2025]

## Resultados que vienen al caso

- **Enanas marrones:** Rustamkulov et al. 2026 (ApJ 1009, 185) sacaron espectros de 0.75 a 5 µm de 37
  enanas marrones cercanas; encuentran agua, CO₂, CO y metano. De WISE 0855: «sólo el flujo por encima de
  3.9 µm se detecta de forma confiable». Usaron posiciones **corregidas por movimiento propio**.
- **Gagné et al. 2026** (arXiv:2604.22012): espectros de **6,003 enanas ultrafrías** con una herramienta
  para fuentes que se mueven rápido. Seguir objetos con movimiento propio en SPHEREx ya se hace.
- **3I/ATLAS:** IRSA publica todas las imágenes del cometa con su posición predicha en cada una: un
  ejemplo oficial de seguir algo que se mueve. [IRSA, colección de 3I/ATLAS]
- **Cosas que cambian de brillo:** ya se usa para clasificar estallidos FU Ori y novas
  (arXiv:2602.07129).

## Quién está detrás

Investigador principal: Jamie Bock (Caltech). Gestión: JPL, para la División de Astrofísica de la NASA.
Nave y telescopio: BAE Systems. Datos: el SPHEREx Science Data Center en IPAC; archivo: **IRSA**
(NASA/IPAC). Participan 13 instituciones de EE. UU., Corea y Taiwán. [JPL Management]

## Fuentes

- **[By the Numbers]** NASA, *SPHEREx By the Numbers* (11 mar 2025): https://science.nasa.gov/blogs/spherex/2025/03/11/nasas-spherex-by-the-numbers/
- **[JPL Quick Facts / Management]** https://www.jpl.nasa.gov/press-kits/spherex/quick-facts/ · https://www.jpl.nasa.gov/press-kits/spherex/management/
- **[JPL dic 2025]** Primer mapa del cielo: https://www.jpl.nasa.gov/news/nasas-spherex-observatory-completes-first-cosmic-map-like-no-other/
- **[Caltech]** https://spherex.caltech.edu/ · [Instrument](https://spherex.caltech.edu/page/instrument) · [Survey](https://spherex.caltech.edu/page/survey) · [noticias](https://spherex.caltech.edu/news)
- **[IRSA]** https://irsa.ipac.caltech.edu/Missions/spherex.html
- **[Supp.]** *SPHEREx Explanatory Supplement* v2.1 (10 nov 2026): https://irsa.ipac.caltech.edu/data/SPHEREx/docs/SPHEREx_Expsupp.pdf
- Bock et al. 2026, ApJ 999, 139 — https://arxiv.org/abs/2511.02985
- Korngut et al. 2026 — https://arxiv.org/abs/2603.29835
- Rustamkulov et al. 2026, ApJ 1009, 185 — https://arxiv.org/abs/2607.00543
- Gagné et al. 2026 — https://arxiv.org/abs/2604.22012
- DR1 disponible (12 nov 2026): https://spherex.caltech.edu/news/spherex-data-release-1-dr1-is-now-available-at-irsa
- NASA, 2025 Astrophysics Senior Review: https://assets.science.nasa.gov/content/dam/science/astro/documents/senior-review-of-operating-missions/2025/2025_Astrophysics_Senior_Review_Report.pdf
