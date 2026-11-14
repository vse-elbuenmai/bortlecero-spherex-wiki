# Wiki de SPHEREx · Bortle Cero — contrato del repo

Wiki de consulta, en Markdown y en español, del equipo Bortle Cero para el reto Planet X and SPHEREx
del NASA Space Apps Challenge 2026. **Es público.** El código y las decisiones del proyecto viven en
otro repo: [vse-elbuenmai/bortlecero-spaceapps](https://github.com/vse-elbuenmai/bortlecero-spaceapps).

Vale para cualquier persona o agente (Claude Code, Codex) que edite aquí.

## Reglas

1. **Cada dato lleva su fuente y su fecha.** Fuente original (IRSA, el Explanatory Supplement, un
   paper, SIMBAD, Gaia…), con enlace. Si no se pudo comprobar, se marca **(sin verificar)**. Si es
   aritmética propia, **(cuenta propia)**. Lo que caduca en días, con ⏳.
2. **Nada de datos personales:** ni nombres del equipo, ni correos, ni teléfonos, ni rutas de las
   computadoras de nadie, ni secretos.
3. **El wiki no decide la solución.** Las reglas de Space Apps piden que la idea de cómo resolver el
   reto sea del equipo («AI should not be used to come up with your idea of how to solve the
   challenge»). Aquí van hechos, trampas, enlaces y números; no recomendaciones de enfoque, de stack o
   de funciones. Lo que el equipo decida se escribe en el repo del proyecto, y aquí sólo se enlaza.
4. **No se copia código ni texto de repos de otros equipos del hackatón**, ni se enlazan.
5. **Nada de logos, banderas ni identificadores de misión de la NASA** en imágenes del wiki. Las
   imágenes generadas con IA, si alguna vez hay, llevan marca de agua visible.
6. **Idioma:** español, lenguaje simple. Los nombres técnicos, las claves de encabezado y las citas
   literales quedan como en la fuente.
7. **El estado externo se verifica en vivo** antes de cambiarlo aquí (estado de un servicio, conteos de
   imágenes, versiones). Si cambias un dato, cambia también la fecha de verificación de la página.

## Cómo se trabaja

- Rama propia (`<nombre>/<tema>`, `claude/<tema>`, `codex/<tema>`) y PR a `main`. Nadie commitea directo
  a `main`.
- Una página por tema. Si añades una, enlázala desde el índice del [README.md](README.md) **y** desde
  [`_sidebar.md`](_sidebar.md) (con ruta que empiece en `/`): el buscador de la versión web sólo indexa
  las páginas que están en el menú lateral.
- La versión web es [`index.html`](index.html) (Docsify, sin build), publicada con GitHub Pages desde
  `main`. Los enlaces entre páginas van relativos y a archivos `.md`; a lo que no sea Markdown
  (`LICENSE`, imágenes externas) se enlaza con la URL completa de GitHub.
- Cada página empieza con su título, una línea de qué cubre y **cuándo se verificó**, y termina con sus
  fuentes.
- Lo generado con IA se declara en el commit con el trailer `Co-Authored-By`.
- Fin de línea LF (lo fija `.gitattributes`): el equipo trabaja en Windows y Linux.
