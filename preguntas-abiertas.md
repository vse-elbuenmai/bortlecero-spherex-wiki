# Preguntas abiertas y contradicciones

Lo que no se pudo averiguar y donde las fuentes no coinciden. Al 13 nov 2026, con lo revisado el 14 nov.
Si resuelves una, muévela a la página que toca, con su fuente y su fecha.

## Sin respuesta

- Si IRSA publica **límites de uso** para el SIA y los recortes: no aparecen en la guía del archivo ni en
  las páginas de las interfaces.
- Un **índice de imágenes por posición** fuera del SIA y el TAP (por ejemplo, un archivo descargable con
  los polígonos de todas las exposiciones).
- **Recortes servidos desde S3**: no existen hoy.
- Si WISE 0855 se ve en **una sola foto** de las bandas 5–6 o sólo apilando: está en el borde de la
  sensibilidad ([objetos/wise-0855.md](objetos/wise-0855.md)). Se sabe mirando los datos.
- El **brillo de Eps Indi B y de RW Aurigae en 3–5 µm** con fuente verificada.
- El **periodo y la fase actuales de R Draconis**: los elementos del GCVS son de 1981.
- Si el pase de noviembre de 2026 de WISE 0855 y Eps Indi B saldrá antes del domingo: con ~4 semanas de
  retraso, no.
- Cualquier decisión oficial de **extender la misión**.
- La respuesta oficial a la pregunta [#1924](https://github.com/nasa/spaceapps/discussions/1924) de
  Connect (reutilizar código propio anterior al hackatón).

## Las fuentes no coinciden

| Dato | Versiones | Cuál usar |
|---|---|---|
| Campo de visión | 11° × 3.5° · 11.3° × 3.5° · 11.5° × 3.5° | 2 × (3.5° × 11.3°), de la página del instrumento |
| Resolución por banda | Caltech: 41/41/41/35/110/130 · IRSA: 39/41/41/35/112/128 | IRSA (medida en vuelo) |
| Píxel | 6.2″ · 6.15″ | 6.15″ para cálculos; 6.2″ es el redondeo |
| Ángulo mínimo al Sol | 91° (nota pública) · 93.5° (paper) | el paper |
| Fecha de lanzamiento | 11 mar 2025 (hora de California) · 12 mar 2025 (UTC) | los archivos usan UTC |
| Temperatura | «−210 °C» · 45 K y 62 K | 45 K (MWIR) y 62 K (SWIR) |
| Tiempo de exposición | 116.9 s (paper) · 113.58 s (Supp. y SIA) | el del encabezado de cada archivo |
| Línea de helio | hasta 50× la luz zodiacal (paper) · hasta 30× (Supp.) | «decenas de veces» |
| Distorsión en las esquinas | «hasta 15 px (~90″)» y «~13 px o ~80″», las dos en el Supp. §4.2.2 | «más de 10 píxeles» |
| Tamaño de un archivo | 65 MB medido · ~67 MB (Supp.) · ~70 MB (guía del archivo) | el medido |
| Canales vacíos del cubo | «canales 51 y 52» (Supp., cuenta desde 1) · «capas 50 y 51» (HiPS, cuenta desde 0) | son los mismos: banda 3 canal 17 y banda 4 canal 1 |
| Licencia de Aladin Lite | LGPL-3.0 (GitHub) · GPL-3 (`package.json` de npm) | citar la del repositorio y anotar la diferencia |
| Tipo espectral de WISE 0855 | Y2 (SIMBAD) · «~Y4?» (Rustamkulov et al. 2026) | «enana Y, la más fría conocida» |
| Enanas marrones en Rustamkulov et al. | 37 (arXiv y nota de la NASA) · 33 (índice de IOP) | 37 |

## Fuentes

Las de cada dato, en su página. Las contradicciones salen de comparar el paper de la misión (Bock et al.
2026), el Explanatory Supplement v2.1, las páginas de Caltech e IRSA y mediciones directas del 13 nov.
