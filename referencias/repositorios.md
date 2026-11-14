# Repositorios y librerías

Repos que conviene conocer: oficiales, de ciencia con SPHEREx, la familia de WiseView y librerías.
Revisados el 13 nov 2026 con la API de GitHub (sólo metadatos y el inicio del README; no se descargó
ninguno). La descripción sale del propio repositorio. ⏳ Licencias y actividad pueden cambiar.

**Antes de usar cualquiera:** tiene que ser de código abierto, se cita en la entrega y se respeta su
licencia ([citas-y-licencias.md](citas-y-licencias.md#4-programas-y-librerías)). Los que dicen «sin
licencia» no dan permiso de reutilizar su código.

## 1. Oficiales de la misión y de IRSA

| Repositorio | Qué es | Licencia |
|---|---|---|
| [Caltech-IPAC/irsa-tutorials](https://github.com/Caltech-IPAC/irsa-tutorials) | los tutoriales de IRSA; la carpeta `tutorials/spherex` tiene los seis de SPHEREx. **Recurso oficial del reto** | BSD-3 |
| [Caltech-IPAC/spherex-archive-documentation](https://github.com/Caltech-IPAC/spherex-archive-documentation) | la guía del archivo de SPHEREx | BSD-3 |
| [Caltech-IPAC/spherex-pipelines](https://github.com/Caltech-IPAC/spherex-pipelines) | el pipeline oficial de los niveles 1 a 3: el código que produce las imágenes. Referencia para entender astrometría, banderas y fotometría | BSD-3 |
| [SPHEREx/Public-products](https://github.com/SPHEREx/Public-products) | desempeño previsto del equipo científico: sensibilidad por canal | sin licencia |
| [SPHEREx/SPHEREx-Visualizer-Lite](https://github.com/SPHEREx/SPHEREx-Visualizer-Lite) | visualizador ligero de la cobertura del sondeo | sin licencia |
| [Caltech-IPAC/firefly](https://github.com/Caltech-IPAC/firefly) | la librería web de los visores de IRSA | ver repo |
| [Caltech-IPAC/firefly_client](https://github.com/Caltech-IPAC/firefly_client) | cliente de Python para Firefly; lo usa el tutorial del cubo | ver repo |
| [Caltech-IPAC/Montage](https://github.com/Caltech-IPAC/Montage) | el motor clásico de mosaicos y reproyección de IPAC | ver repo |

## 2. Ciencia con SPHEREx hecha por investigadores (anteriores al hackatón)

Herramientas de investigación, no proyectos del reto.

| Repositorio | Qué hace | Licencia |
|---|---|---|
| [jgagneastro/SPIFF](https://github.com/jgagneastro/SPIFF) | espectrofotometría de **fuentes que se mueven rápido**; la herramienta de Gagné et al. 2026 | MIT |
| [WenkeRen/spxquery](https://github.com/WenkeRen/spxquery) | consultar y bajar datos de SPHEREx y armar series en el tiempo | MIT |
| [banados/spherex-tools](https://github.com/banados/spherex-tools) | consulta a IRSA, descarga de archivos o recortes por lotes, fotometría de apertura | MIT |
| [rkiman/spherexminer](https://github.com/rkiman/spherexminer) | para un objeto con **movimiento propio**: busca sus imágenes, mueve la posición a la fecha de cada una y arma el espectro | MIT |
| [hbahk/spherex-retrieval](https://github.com/hbahk/spherex-retrieval) | bajada de recortes preparada para fotometría forzada | MIT |
| [hbahk/tractorjax-spherex](https://github.com/hbahk/tractorjax-spherex) | fotometría forzada sobre nivel 2 | GPL-3.0 |
| [huntbrooks85/xcavation](https://github.com/huntbrooks85/xcavation) | espectros por fotometría de apertura | MIT |
| [leejjoon/ssiaat](https://github.com/leejjoon/ssiaat) | imágenes de nivel 2 como tablas, reproyectadas a una rejilla común | sin licencia |
| [mpi-astronomy/spherex-tools](https://github.com/mpi-astronomy/spherex-tools) | scripts y cuadernos para datos de SPHEREx | BSD-3 |
| [yongjungkim/spherexss](https://github.com/yongjungkim/spherexss) | «SPHEREx Simple Simulator» | Apache-2.0 |

Los espectros de Gagné et al. 2026 están públicos en **mocadb.ca** (según el resumen del paper).

## 3. WiseView y su familia

| Repositorio | Qué es | Licencia |
|---|---|---|
| [backyardworlds/wiseview](https://github.com/backyardworlds/wiseview) | el código de WiseView ([contexto/wiseview.md](../contexto/wiseview.md)) | **dominio público** (Unlicense) |
| [fkiwy/unTimely_Catalog_explorer](https://github.com/fkiwy/unTimely_Catalog_explorer) | búsqueda y visualización del catálogo unTimely; parpadeos en GIF. ASCL 2211.005 | ver repo |
| [dstndstn/unwise-coadds](https://github.com/dstndstn/unwise-coadds) | cómo se hacen los apilados de unWISE | GPL-2.0 |
| [coolneighbors/flipbooks](https://github.com/coolneighbors/flipbooks) | los «flipbooks» de Backyard Worlds: Cool Neighbors, con la API de WiseView | sin licencia |
| [zooniverse/front-end-monorepo](https://github.com/zooniverse/front-end-monorepo) | la plataforma donde vive Backyard Worlds | Apache-2.0 |

## 4. Python para astronomía

| Repositorio | Para qué | Licencia |
|---|---|---|
| [astropy/astropy](https://github.com/astropy/astropy) | FITS, coordenadas, tiempos, WCS con SIP, recortes, estirados | BSD-3 |
| [astropy/reproject](https://github.com/astropy/reproject) | llevar cada imagen a una rejilla común | BSD-3 |
| [astropy/photutils](https://github.com/astropy/photutils) | centroides, detección y fotometría | BSD-3 |
| [astropy/astroquery](https://github.com/astropy/astroquery) | IRSA, SIMBAD, Gaia, VizieR desde Python | BSD-3 |
| [astropy/pyvo](https://github.com/astropy/pyvo) | SIA y TAP del Observatorio Virtual | BSD-3 |
| [astropy/regions](https://github.com/astropy/regions) | regiones en el cielo; archivos `.reg` de DS9 | BSD-3 |
| [astropy/astropy-healpix](https://github.com/astropy/astropy-healpix) | HEALPix: qué mosaico del cubo contiene una coordenada | BSD-3 |
| [spacetelescope/astrocut](https://github.com/spacetelescope/astrocut) | recortes de imágenes y cubos, también desde la nube | ver repo |
| [fsspec/s3fs](https://github.com/fsspec/s3fs) | leer archivos de S3 por rangos | BSD-3 |
| [liberfa/pyerfa](https://github.com/liberfa/pyerfa) | las rutinas de astrometría que usa Astropy (movimiento propio y paralaje) | BSD-3 |
| [dstndstn/tractor](https://github.com/dstndstn/tractor) | fotometría forzada por ajuste de modelo; la usa la herramienta de espectrofotometría de IRSA | ver repo |
| [dirac-institute/kbmod](https://github.com/dirac-institute/kbmod) | búsqueda de objetos que se mueven apilando a lo largo de trayectorias («shift and stack») | BSD-2 |
| [sep-developers/sep](https://github.com/sep-developers/sep) | detección de fuentes al estilo SExtractor; **no instaló** en Python 3.14 + Windows (13 nov) | ver repo |

## 5. Para la web

| Repositorio | Para qué | Licencia |
|---|---|---|
| [cds-astro/aladin-lite](https://github.com/cds-astro/aladin-lite) | visor del cielo en el navegador; muestra HiPS, catálogos y FITS | LGPL-3.0 (npm dice GPL-3) |
| [cds-astro/ipyaladin](https://github.com/cds-astro/ipyaladin) | Aladin Lite dentro de un cuaderno | BSD-3 |
| [astrojs/fitsjs](https://github.com/astrojs/fitsjs) | lector de FITS en JavaScript; **sin cambios desde 2015** | MIT |
| [cosinekitty/astronomy](https://github.com/cosinekitty/astronomy) | «Astronomy Engine»: posiciones del Sol, la Tierra y los planetas en JS, Python, C y C# | MIT |
| [plotly/plotly.js](https://github.com/plotly/plotly.js) | gráficas interactivas | MIT |
| [pyodide/pyodide](https://github.com/pyodide/pyodide) | Python en el navegador (WebAssembly); trae Astropy entre sus paquetes (verificar versión) | MPL-2.0 |

## 6. Visores de escritorio y otros

| Repositorio | Qué es | Licencia |
|---|---|---|
| [SAOImageDS9/SAOImageDS9](https://github.com/SAOImageDS9/SAOImageDS9) | DS9 | GPL-3.0 |
| [spacetelescope/jdaviz](https://github.com/spacetelescope/jdaviz) | visores del STScI para cuadernos; Imviz alinea por coordenadas y parpadea | BSD-3 |
| [ejeschke/ginga](https://github.com/ejeschke/ginga) | visor de FITS en Python | BSD-3 |
| [ericmandel/js9](https://github.com/ericmandel/js9) | **archivado**, sin mantenimiento | — |
| [asc-csa/NEOSSAT_Tutorial](https://github.com/asc-csa/NEOSSAT_Tutorial) | el tutorial de NEOSSat de los Resources | ver repo |
| [nasa/spaceapps](https://github.com/nasa/spaceapps) | el repositorio cuyas Discussions son Space Apps Connect | — |

## 7. Repositorios de otros equipos del hackatón: no se abren

En GitHub hay más de cien repos del reto (varios creados semanas antes del evento). **No se abre su
código ni se copia**, y no se enlazan aquí: la idea de la solución tiene que ser del equipo.
