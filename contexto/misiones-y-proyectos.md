# Misiones y proyectos relacionados

Contexto para entender el reto y para las preguntas del jurado. Cada dato dice si se verificó (con su
fecha) o si va **(sin verificar)**: esos se comprueban antes de decirlos en público.

## El linaje del reto: de la placa de vidrio al navegador

| Año | Quién | Con qué | Qué encontró |
|---|---|---|---|
| 1930 | Clyde Tombaugh, Observatorio Lowell | comparador de parpadeo: dos placas de la misma zona, vistas alternadas | Plutón (sin verificar: 18 feb 1930) |
| 2010–2024 | WISE y NEOWISE (NASA) | todo el cielo en infrarrojo, una y otra vez | miles de enanas marrones cercanas; WISE 0855 (2014) |
| 2017 → | **Backyard Worlds: Planet 9** | voluntarios parpadeando imágenes de WISE en Zooniverse y en WiseView | más de 3,000 enanas marrones |
| 2025 → | **SPHEREx** | todo el cielo cada seis meses, en 102 colores | el reto |
| 2026 → | **The Rogue Worlds Project** | voluntarios sobre datos de SPHEREx | planetas errantes y enanas marrones en cúmulos jóvenes |

## WISE, NEOWISE y sus derivados

- **WISE** (NASA, lanzado en dic 2009): telescopio de 40 cm, todo el cielo en 3.4, 4.6, 12 y 22 µm (W1 a
  W4). Píxel de 2.75″, nitidez de ~6″ en W1 y W2 (verificado el 10 nov). Se quedó sin refrigerante en 2010
  y siguió con W1 y W2 (sin verificar).
- **NEOWISE:** la misma nave, reactivada para buscar asteroides; tomó su última imagen el **31 jul 2024**
  y la NASA apagó su transmisor el 8 ago 2024 (verificado el 10 nov, JPL).
- **Por qué importa:** W1 y W2 caen en las bandas 4 y 6 de SPHEREx. WISE da 14 años de historia justo
  antes de que empiece SPHEREx.
- **AllWISE:** catálogo e imágenes de 2010–2011. En IRSA: tabla `allwise_p3as_psd`.
- **unWISE** (Lang 2014; Meisner et al. 2017): apilados de WISE sin emborronar, y su versión por visita
  (un apilado cada seis meses). Es lo que parpadea WiseView.
- **CatWISE2020** (Marocco et al. 2021): movimientos propios medidos sobre ocho años de WISE. En IRSA:
  `catwise_2020`. Los objetos muy rápidos salen partidos en varias entradas (pasa con WISE 0855).
- **unTimely** (Meisner et al. 2023): detecciones por época.

## Backyard Worlds y The Rogue Worlds Project

- **Backyard Worlds: Planet 9** — backyardworlds.org, en Zooniverse desde feb 2017; lo dirige Marc
  Kuchner (NASA Goddard) y lo cofundó el AMNH (verificado el 10 nov).
- **El resultado grande** (NASA, 5 may 2026; verificado el 13 nov): los voluntarios descubrieron **más
  de 3,000 enanas marrones**, lo que duplica la población conocida. Participaron unas **200,000
  personas** durante 10 años. El paper tiene 75 autores, **61 de ellos voluntarios** (Schneider et al.
  2026, AJ, arXiv:2604.01323). La nota dice que algunos voluntarios construyeron sus propias herramientas
  de búsqueda: WiseView nació así.
- **The Rogue Worlds Project** (verificado el 13 nov): «Activating volunteers to uncover the hidden
  population of super Jupiters with SPHEREx». Investigadora principal: Jacqueline Faherty (AMNH),
  cofundadora de Backyard Worlds. Seleccionado por la NASA el 28 oct 2026 entre 19 propuestas de ciencia
  ciudadana. Es Backyard Worlds pasando de WISE a SPHEREx.
- **Gagné et al. 2026** (arXiv:2604.22012; verificado el 13 nov): con datos de SPHEREx y una herramienta
  para fuentes que se mueven rápido, espectros de 0.75 a 5 µm de **6,003 enanas ultrafrías**, 947 nuevas.
  Unos 137 autores, la mayoría de Backyard Worlds.

## Gaia

- Misión de la **ESA** que midió posición, paralaje y movimiento propio de ~1,800 millones de estrellas
  en luz visible. **DR3** (jun 2022) da las posiciones en la **época 2016.0** (verificado: columna
  `ref_epoch`). El enunciado pide DR3.
- Es la **referencia astrométrica del propio pipeline de SPHEREx**, con el movimiento propio aplicado a la
  fecha de cada imagen. [Supp. §3.2.8]
- **Lo que no ve:** lo muy frío. WISE 0855 no está en Gaia; Eps Indi B sí, con G = 18 y mal ajuste (RUWE
  4.3) por ser doble.
- **Dónde consultarla:** archivo de la ESA (`gea.esac.esa.int`, tabla `gaiadr3.gaia_source`); copia en el
  TAP de IRSA (`gaia_dr3_source`); el recurso del reto enlaza la página de MAST.
- Gaia es de la ESA: en la entrega va en «Space Agency Partner Data and Other References», no como dato
  de la NASA.
- La DR4 está anunciada para dic 2026 (sin verificar).

## 2MASS

Sondeo de todo el cielo en J, H y Ks desde tierra, hecho hacia 1997–2001 (sin verificar). En IRSA: tabla
`fp_psc` y HiPS `CDS/2MASS/…`. Sus posiciones son de ~1998–2000, así que una estrella rápida aparece muy
lejos de donde está hoy: Barnard, ~280″ (cuenta propia).

## Planeta X y Planeta Nueve: lo que hay detrás del título

Casi todo este bloque va **(sin verificar)**, salvo donde se indica.

- **«Planeta X»** era el planeta que Percival Lowell buscaba más allá de Neptuno a principios del siglo
  XX. La búsqueda llevó a Plutón (1930), que resultó demasiado pequeño para ser ese planeta.
- **«Planeta Nueve»** es la hipótesis moderna (Batygin y Brown 2016): un planeta de varias masas
  terrestres, a cientos de unidades astronómicas, que explicaría por qué las órbitas de algunos objetos
  lejanos están alineadas. No se ha observado.
- **Búsquedas en infrarrojo:** WISE descartó un Saturno hasta ~10,000 UA y un Júpiter hasta ~26,000 UA
  (Luhman 2014); Backyard Worlds lleva «Planet 9» en el nombre por eso.
- **Búsqueda reciente** (verificado el 13 nov, por resumen de búsqueda): Socas-Navarro y Trujillo 2026
  (*Open Journal of Astrophysics* 9) buscaron por paralaje en ~98 grados cuadrados y no hallaron
  candidatos.
- **¿Podría SPHEREx ver el Planeta Nueve?** (razonamiento propio) Difícilmente: a cientos de UA sería muy
  frío y su luz propia sale en el infrarrojo lejano, no entre 1 y 5 µm; lo que vería es luz del Sol
  reflejada, muy por debajo de su límite. Lo que SPHEREx sí aporta son enanas marrones frías y cercanas,
  como WISE 0855.

## Los recursos de la agencia canadiense

- **NEOSSat:** microsatélite canadiense dedicado a asteroides, cometas, satélites y basura espacial;
  imágenes en luz visible.
- **CADC:** el centro canadiense de datos astronómicos.
- Son opcionales y no sustituyen al dato de la NASA que exige la regla de premios globales.

## Otros nombres que pueden salir

| Nombre | Qué es | Relación |
|---|---|---|
| **3I/ATLAS** | el tercer objeto interestelar; SPHEREx lo observó en ago y dic de 2025 | IRSA publica la tabla de sus imágenes con su posición predicha en cada una |
| **MOST** | herramienta de IRSA para objetos del sistema solar | no sirve para estrellas |
| **JWST** | infrarrojo con muchísimo detalle en campos diminutos | campo miles de veces más chico que SPHEREx |
| **PUNCH** | cuatro satélites que estudian el viento solar | viajaron en el mismo cohete que SPHEREx |
| **TESS** | busca planetas por tránsitos | rescató al candidato a planeta enano 2026 ED138 apilando a lo largo de su trayectoria |
| **Rubin** (Chile) | sondeo en luz visible, muy profundo | del que se espera que encuentre o descarte el Planeta Nueve (sin verificar) |
| **Pan-STARRS** | sondeo en visible desde Hawái | WiseView lo muestra como referencia |
| **Zooniverse** | la plataforma de ciencia ciudadana | donde vive Backyard Worlds |
| **CDS** (Estrasburgo) | SIMBAD, VizieR, Aladin | ⏳ caído por un incidente de ciberseguridad ([servicios.md](../servicios.md)) |
| **IPAC / IRSA** (Caltech) | el archivo infrarrojo de la NASA | donde vive SPHEREx; también WISE, 2MASS y Spitzer |
| **MAST** (STScI) | el archivo de Hubble, JWST y TESS | el recurso de Gaia del reto enlaza ahí |

## Fuentes

- NASA, voluntarios duplican la población de enanas marrones (5 may 2026): https://science.nasa.gov/get-involved/citizen-science/nasa-volunteers-double-known-population-of-brown-dwarfs/
- NASA, 19 proyectos de ciencia ciudadana (28 oct 2026): https://science.nasa.gov/get-involved/citizen-science/nasa-selects-19-new-citizen-science-proposals-in-2026/
- AMNH, lanzamiento de Backyard Worlds (feb 2017): https://amnh.org/about/press-center/public-invited-to-search-for-new-nearby-worlds
- JPL, despedida de NEOWISE: https://www.jpl.nasa.gov/videos/farewell-to-neowise-nasas-asteroid-hunting-telescope/
- IPAC, WISE All-Sky Explanatory Supplement §I.1: https://wise2.ipac.caltech.edu/docs/release/allsky/expsup/sec1_1.html
- Gagné et al. 2026 — https://arxiv.org/abs/2604.22012 · Schneider et al. 2026 — https://arxiv.org/abs/2604.01323
- Gaia DR3: https://www.cosmos.esa.int/web/gaia/dr3
