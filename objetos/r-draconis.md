# R Draconis

Objeto de prueba de **cambio de brillo**. El que más imágenes tiene, porque cae en un campo profundo.
Verificado el 13 nov 2026 (Gaia DR3 en la ESA, SIMBAD en Harvard, GCVS por el VizieR de Harvard, SIA de
IRSA).

| Dato | Valor | Fuente |
|---|---|---|
| Qué es | variable Mira: gigante roja que pulsa | SIMBAD (`Mi*`, M4.5–6+e) |
| Gaia DR3 | `1648328016354496384` | ESA |
| Posición (época 2016.0) | 248.167378°, +66.755007° (16 32 40.2, +66 45 18) | Gaia DR3 |
| Movimiento propio | −20.64, +6.15 mas/año | Gaia DR3 |
| Paralaje | 1.251 ± 0.065 mas (~800 pc) | Gaia DR3 |
| Brillo (Vega) | G 6.37 · J 3.71 · H 3.13 · K 2.23 | SIMBAD |
| Periodo | **245.6 días**; V de 6.7 a 13.2; tipo M5e–M9eIII; máximo de referencia JD 2444779 | GCVS |

## En SPHEREx: el borde del campo profundo del polo norte eclíptico

| Colección | Imágenes | Fechas | Detectores |
|---|---|---|---|
| `spherex_dr1` + `spherex_qr3` (todo el cielo) | 543 | 16 may–22 jul 2025 · 17 oct 2025–13 ene 2026 · 22 abr–16 jul 2026 | los seis |
| `spherex_dr1_deep` + `spherex_qr3_deep` | **1,954** | 24 abr 2025 → 27 sep 2026 | **sólo 1, 3, 4 y 6** (≈ 490 cada uno) |

- **~2,500 imágenes en 17 meses**, más de dos ciclos completos de la estrella.
- Imágenes del campo profundo por mes: abr 2025 58 · may 29 · ago 14 · sep 188 · oct 46 · nov 12 ·
  feb 2026 112 · mar 500 · abr 231 · may 35 · jul 72 · ago 432 · sep 225. El hueco más largo va del
  8 may al 29 ago 2025; el sondeo de todo el cielo cubre parte de él.
- Cae en el borde del campo profundo: por eso sólo la tocan los detectores de los extremos.
- **Saturación:** K = 2.23 Vega (≈ 4.1 AB): siete magnitudes por encima del inicio de no linealidad
  (cuenta propia). Satura siempre y en todas las bandas; el núcleo es NaN y el halo BLOOM es grande. Un
  número fiable de su brillo no sale del centro.
- **Máximos esperados** con los elementos del GCVS (cuenta propia): hacia el 8 nov 2025, el 12 jul 2026
  y el 14 mar 2027. Esos elementos son de 1981 y las Miras se adelantan y se atrasan: pueden estar
  corridos semanas. La fase real se ve en la curva de luz de la AAVSO (https://www.aavso.org/LCGv2/).

## Para el jurado (sin verificar)

En una Mira el cambio en infrarrojo es mucho menor que en visible (alrededor de una magnitud en K contra
más de seis en V), y el máximo infrarrojo llega algo después del visible. **Comprobar antes de decirlo.**

## Fuentes

- Gaia DR3, archivo de la ESA: https://gea.esac.esa.int/archive/ (Gaia Collaboration, Vallenari et al. 2023)
- SIMBAD, espejo de Harvard: https://simbad.cfa.harvard.edu/simbad/sim-id?Ident=R%20Dra (Wenger et al. 2000)
- GCVS (Samus et al. 2017), por https://vizier.cfa.harvard.edu
- SIA de IRSA (`spherex_dr1`, `spherex_qr3`, `spherex_dr1_deep`, `spherex_qr3_deep`), 13 nov 2026.
