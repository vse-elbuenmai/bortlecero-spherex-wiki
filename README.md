# Wiki de SPHEREx · Bortle Cero

Wiki de consulta del equipo **Bortle Cero** (sede presencial de Guadalajara) para el reto
[Planet X and SPHEREx](https://www.spaceappschallenge.org/2026/challenges/planet-x-and-spherex/) del
NASA Space Apps Challenge 2026 (14 y 15 de noviembre de 2026).

Aquí está lo que hay que saber de la misión, de sus datos, de los cinco objetos de prueba y del reto,
con la fuente de cada dato. Sirve para resolver dudas rápido durante el hackatón sin tener que volver a
investigar.

**Versión web con buscador:** https://vse-elbuenmai.github.io/bortlecero-spherex-wiki/

> **Este wiki no es la solución.** No tiene código ni decisiones de diseño. La idea de cómo resolver el
> reto la decide el equipo, y lo que se decide se escribe en el repo del proyecto,
> [bortlecero-spaceapps](https://github.com/vse-elbuenmai/bortlecero-spaceapps).
>
> Proyecto independiente del equipo. No está afiliado a la NASA ni respaldado por ella.

## Índice

| Si necesitas… | Abre |
|---|---|
| Qué pide el reto, sus recursos, sus reglas y el reloj | [reto/el-reto.md](reto/el-reto.md) |
| En qué va nuestro proyecto y dónde se decide cada cosa | [reto/el-proyecto.md](reto/el-proyecto.md) |
| **Las trampas que rompen un parpadeo ingenuo** | [trampas.md](trampas.md) |
| Qué es SPHEREx: nave, cámara, bandas, órbita, metas, cronología | [spherex/la-mision.md](spherex/la-mision.md) |
| Cómo barre el cielo, por qué cada foto ve otro color y por qué a veces sale girada | [spherex/como-observa.md](spherex/como-observa.md) |
| Qué entregas de datos hay (DR1, QR3…) y cuál usar | [datos/entregas.md](datos/entregas.md) |
| Qué trae un archivo: hojas, encabezado, canales, banderas, saturación | [datos/el-archivo-fits.md](datos/el-archivo-fits.md) |
| Cómo se llega a los datos: SIA, TAP, recortes, S3, CORS, herramientas de IRSA | [datos/como-llegar.md](datos/como-llegar.md) |
| El cubo de todo el cielo en 102 canales | [datos/cubo-de-todo-el-cielo.md](datos/cubo-de-todo-el-cielo.md) |
| Los cinco objetos de prueba, uno por uno | [objetos/README.md](objetos/README.md) |
| WiseView, el modelo que señala la NASA | [contexto/wiseview.md](contexto/wiseview.md) |
| WISE, Backyard Worlds, Gaia, 2MASS, Planeta X y Planeta Nueve | [contexto/misiones-y-proyectos.md](contexto/misiones-y-proyectos.md) |
| Qué servicio está caído y su respaldo ⏳ | [servicios.md](servicios.md) |
| Cómo se cita cada cosa y qué licencia tiene | [referencias/citas-y-licencias.md](referencias/citas-y-licencias.md) |
| Repositorios y librerías útiles | [referencias/repositorios.md](referencias/repositorios.md) |
| Qué significa cada palabra rara (RA/Dec, paralaje, FITS, WCS, HiPS…) | [glosario.md](glosario.md) |
| Lo que no sabemos y donde las fuentes no coinciden | [preguntas-abiertas.md](preguntas-abiertas.md) |

## Cómo leerlo

- Cada página dice **cuándo se verificó** y contra qué fuente. La mayor parte se comprobó la noche del
  13 de noviembre de 2026; lo revisado después lleva su fecha.
- ⏳ marca lo que **caduca** en días: estado de un servicio, conteos de imágenes, versiones. Antes de
  apoyarse en eso, se vuelve a comprobar en vivo.
- **(cuenta propia)** marca aritmética hecha a partir de datos verificados. Sirve para orientarse; el
  número que vaya a la entrega se recalcula con los datos.
- **(sin verificar)** marca un dato que no se comprobó contra su fuente. No se dice en público sin
  comprobarlo antes.
- Las horas son de Guadalajara (UTC−6) salvo que diga UTC.
- **En la entrega no se cita este wiki:** se cita la fuente original de cada dato. Los enlaces están en
  cada página y en [referencias/citas-y-licencias.md](referencias/citas-y-licencias.md).

## Cómo se hizo (uso de IA)

El texto lo redactó **Claude Code (Anthropic)** el 14 de noviembre de 2026 a partir de las notas de
estudio que el equipo reunió antes del hackatón (del 5 al 13 de noviembre). Esas notas también se
armaron con ayuda de Claude y se verificaron contra las fuentes oficiales que se citan. Las revisa el
equipo. Los commits hechos con IA llevan el trailer `Co-Authored-By`.

## Cómo contribuir

Cualquiera del equipo puede corregir o añadir. Las reglas están en [AGENTS.md](AGENTS.md); en corto:
rama propia y PR, en español, **cada dato con su fuente y su fecha**, nada de datos personales, y nada
que decida la solución.

## La versión web

El sitio es un solo [`index.html`](https://github.com/vse-elbuenmai/bortlecero-spherex-wiki/blob/main/index.html)
que lee estos mismos Markdown en el navegador y los muestra con menú lateral y buscador. No hay paso de
build: lo que se fusiona a `main` aparece en el sitio en un par de minutos. Se publica con GitHub Pages
desde la raíz de `main`. Los colores y la fuente siguen el `DESIGN.md` del proyecto.

Software que usa:

| Qué | Licencia | Enlace |
|---|---|---|
| Docsify 5.1.0, con su plugin de búsqueda | MIT | https://github.com/docsifyjs/docsify |
| Space Grotesk, de Florian Karsten (vía Fontsource 5.3.0) | SIL Open Font License 1.1 | https://github.com/floriankarsten/space-grotesk |

Para verlo en local: `python -m http.server 3000` en la carpeta del repo y abrir http://localhost:3000.

## Licencia

El texto de este wiki está bajo [Apache 2.0](https://github.com/vse-elbuenmai/bortlecero-spherex-wiki/blob/main/LICENSE), la licencia por defecto de Space Apps. Los datos,
las cifras y las citas pertenecen a sus fuentes (NASA, IPAC/IRSA, Caltech, ESA, CDS y los autores de cada
paper), que se nombran en cada página.
