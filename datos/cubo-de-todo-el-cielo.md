# El cubo de todo el cielo (DR1)

El producto nuevo de DR1: todo el cielo en los 102 canales, como árbol HiPS para ver y como mosaicos
FITS para medir. Verificado el 13 nov 2026 contra el Explanatory Supplement v2.1 («Supp.» §2.5 y §3.4),
la lista de HiPS de IRSA y S3.

## Dos formas del mismo producto

| | Árbol HiPS (para ver) | Mosaicos FITS (los datos) |
|---|---|---|
| Dónde | `https://irsa.ipac.caltech.edu/data/hips/SPHEREx/spherex_allsky_cube` | `…/ibe/data/spherex/dr1/hips5_cube/hips_20261026/Norder5/Dir[N]/Npix[M]_cube.fits`; en S3, `dr1/hips5_cube/hips_20261026/…` |
| Formato | PNG, 102 capas; orden HiPS de 0 a 5 | cubo de 512 × 512 × 102 por mosaico |
| Píxel | 12.9″ en el orden 5 | 12.9″ |
| Tamaño | ~30 KB por imagen | **321 MB por mosaico**, sin comprimir; 12,288 mosaicos de ~1.8° |
| Valores | estirado fijo: asinh entre 0 y 40 MJy/sr | MJy/sr, con la luz zodiacal ya restada |
| CORS | sí (`*`) | sí, en S3 |
| Hojas | — | IMAGE, NHITS (cuántas fotos entraron), FLAGS, SPECTRAL_CHANNELS, WCS-WAVE |

Identificador del HiPS: `ivo://IPAC/P/SPHEREx/DR1/cube`. Un HiPS es como los mosaicos de un mapa web:
imágenes chicas por nivel de zoom, que un visor (Aladin Lite, por ejemplo) pide según lo que se ve.

## Capas y canales

- **Capa = 17 × (banda − 1) + (canal − 1)**, de 0 a 101, en orden de longitud de onda. Las propiedades
  (`…/spherex_allsky_cube/properties`) traen los 102 centros en `data_cube_crval3_arr`.
- **Nombres de las imágenes:** la capa 0 es `Norder5/Dir0/Npix0.png`; las demás, `Npix0_1.png` …
  `Npix0_101.png`. `Dir` agrupa de 10,000 en 10,000.
- **Dos capas vacías:** la 50 y la 51 (banda 3 canal 17 y banda 4 canal 1, junto al dicroico). El Supp.
  las llama «canales 51 y 52» porque cuenta desde 1. Volverán en DR2.

## Lo que hay que saber antes de usarlo

- **Es un promedio, no una película.** Junta más de 1.2 millones de imágenes del 24 abr 2025 al 14 may
  2026. Lo que se mueve sale corrido o duplicado, y lo que cambia de brillo, promediado. Sirve de fondo y
  para ver el espectro medio de un punto; **no muestra cambios en el tiempo**.
- **Trae rayas.** Las líneas de la atmósfera (sobre todo el helio en la banda 1) y las fuentes extensas
  con líneas fuertes dejan franjas que no se promedian. [Supp. §2.5.2]
- IRSA: para medir, usar el FITS y no los PNG; para fotometría de precisión, las imágenes de nivel 2.
- **Cómo se hizo** [Supp. §3.4]: a cada imagen se le resta ZODI, se descartan los píxeles con banderas
  de defecto (todas menos OVERFLOW, SOURCE y OUTLIER, que se propagan), se separan los píxeles por canal
  y se acumulan en la rejilla de salida con el vecino más cercano («histogram-based reprojection»,
  Cukierman et al. 2026).
- Se cita con el DOI [10.26131/IRSA679](https://www.ipac.caltech.edu/doi/10.26131/IRSA679).

## Fuentes

- *SPHEREx Explanatory Supplement* v2.1, §2.5 y §3.4: https://irsa.ipac.caltech.edu/data/SPHEREx/docs/SPHEREx_Expsupp.pdf
- Lista de HiPS de IRSA: https://irsa.ipac.caltech.edu/data/hips/list
- Tutorial del cubo HiPS: https://caltech-ipac.github.io/irsa-tutorials/spherex-hipscube/
- Cukierman et al. 2026, *Spectral Map Making with SPHEREx*, ApJS 286, 22 — https://arxiv.org/abs/2603.25790
