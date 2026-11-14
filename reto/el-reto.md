# El reto: Planet X and SPHEREx

Qué pide el reto, qué recursos da, qué reglas obligan y cómo se juzga. Verificado contra la página del
reto el 13 nov 2026 (Resources revisados de nuevo el 14 nov a las ~13:15, sin cambios).

## Qué pide

Una **herramienta web pública** donde alguien escribe una posición del cielo (RA/Dec) y ve la serie de
imágenes de SPHEREx de ese trozo de cielo como un **parpadeo**, para notar lo que se mueve o cambia de
brillo. Es la técnica de Clyde Tombaugh con Plutón y de Backyard Worlds con WISE, ahora sobre SPHEREx
(ver [contexto/misiones-y-proyectos.md](../contexto/misiones-y-proyectos.md)).

El enunciado dice que «most of the known comets and brown dwarfs were discovered by volunteers in this
manner through projects like backyardworlds.org».

**Objetos de prueba** (fichas en [objetos/](../objetos/README.md)):

| Objeto | Qué debe mostrar |
|---|---|
| Estrella de Barnard | movimiento |
| Epsilon Indi B | movimiento |
| WISE 0855−0714 | movimiento (ojo: las coordenadas del enunciado son de ~2010) |
| RW Aurigae | cambio de brillo |
| R Draconis | cambio de brillo |

Las «consideraciones» del enunciado (sumar y restar fechas, elegir el campo de visión, superponer Gaia,
llevar las coordenadas en la URL, facilidad para actualizar con entregas nuevas, usar las 102 bandas)
están en la página del reto. Varias son funciones que ya tiene WiseView
([contexto/wiseview.md](../contexto/wiseview.md)).

## Recursos oficiales (pestaña Resources)

**NASA Data & Resources.** Para los premios globales hay que usar al menos uno, y que sea la base de la
herramienta, no un adorno.

| Recurso | Enlace | Qué dice la NASA |
|---|---|---|
| NASA/IPAC Infrared Science Archive | https://irsa.ipac.caltech.edu/Missions/spherex.html | «SPHEREx resources» |
| SPHEREx Tutorial Notebooks | https://caltech-ipac.github.io/irsa-tutorials/spherex/ | cuadernos de Python para llegar a los datos |
| WiseView | http://byw.tools/wiseview (sólo http) | «A similar tool made for viewing data from an earlier NASA mission called WISE… Feel free to use it as a model or as inspiration!» |
| Gaia Mission Data | https://archive.stsci.edu/missions-and-data/gaia | «Be sure to use the latest data release (Data Release 3).» |

**Space Agency Partner Resources (CSA, Canadá).** Opcionales; no cuentan como dato de la NASA.

| Recurso | Enlace |
|---|---|
| NEOSSat | https://www.asc-csa.gc.ca/eng/satellites/neossat/ |
| Canadian Astronomy Data Centre (CADC) | https://www.cadc-ccda.hia-iha.nrc-cnrc.gc.ca/en/ |
| NEOSSat Data Tutorial | https://github.com/asc-csa/NEOSSAT_Tutorial |
| NEOSSat Dataset | https://data.asc-csa.gc.ca/dataset/neossat |

No hay un conjunto de datos ya armado para los cinco objetos: se sacan de IRSA
([datos/como-llegar.md](../datos/como-llegar.md)).

## Reglas que pesan

Detalle y fuente en la [guía de entrega](https://www.spaceappschallenge.org/resources/project-submission-guide/),
la [guía de jurado](https://www.spaceappschallenge.org/resources/judging-awards-guide/), las
[reglas de marca](https://www.spaceappschallenge.org/brand) y los
[términos](https://www.spaceappschallenge.org/legal/).

- **La IA se permite, y se declara.** La entrega describe cómo se usó. Imágenes y videos generados
  llevan marca de agua visible. Nada generado usa ni modifica logos, banderas o identificadores de
  misión de la NASA.
- **La idea de la solución es del equipo.** «AI should not be used to come up with your idea of how to
  solve the challenge.»
- **Toda fuente se cita**, aunque sea abierta: «You must cite every source… even if it is open source».
  Si falta una, la NASA puede retirar nominaciones o premios.
- **Datos de la NASA en el centro** para optar a premios globales (ver arriba).
- **Sólo código abierto.** El proyecto se publica abierto (Apache 2.0 por omisión).
- **No apoyarse en código hecho para el reto antes del evento.** Trabajar antes del hackatón puede
  descalificar; antes sólo se vale elegir reto, revisar recursos, investigar y armar equipo.
- **Lo que ve el público va en inglés**: interfaz, README, página del proyecto y slides.
- **Demo:** video de 30 s como máximo (con subtítulos en inglés si se habla español) o hasta 7 slides.
  Pasarse deja al proyecto fuera del juicio global.

## Cómo se juzga

De 1 a 5 en cinco criterios: **Impact, Creativity, Validity, Relevance y Presentation**
([guía de jurado](https://www.spaceappschallenge.org/resources/judging-awards-guide/)).

## El reloj (hora de Guadalajara)

| Cuándo | Qué |
|---|---|
| Sáb 14, ~14:00 | se congela el alcance (decisión del equipo) |
| Sáb 14 y dom 15, 20:00 | cierra la sede; se sigue desde fuera |
| Dom 15, ~21:00 | objetivo del equipo para enviar, con 3–4 horas reservadas para armar la entrega |
| Dom 15, 23:59 | límite en la plataforma; cuenta la última versión enviada |

## Space Apps Connect

El foro oficial son las [Discussions de `nasa/spaceapps`](https://github.com/nasa/spaceapps/discussions).
Ahí contesta el GO Team las dudas de reglas. Los expertos llegan el sábado a las 8:00 de Guadalajara.

## Fuentes

- Página del reto (Details y Resources): https://www.spaceappschallenge.org/2026/challenges/planet-x-and-spherex/ — leída con Playwright el 13 nov y el 14 nov 2026.
- Guías y reglas: enlaces de la sección «Reglas que pesan», leídas el 13 nov 2026.
