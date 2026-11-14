# Estrella de Barnard

Objeto de prueba de **movimiento**. Verificado el 13 nov 2026 (Gaia DR3 en la ESA, SIMBAD en Harvard,
SIA de IRSA).

| Dato | Valor | Fuente |
|---|---|---|
| Nombres | Barnard's Star, GJ 699, V2500 Oph | SIMBAD |
| Gaia DR3 | `4472832130942575872` | ESA |
| Posición (época 2016.0) | 269.448503°, +4.739420° | Gaia DR3 |
| Posición J2000 | 269.452077°, +4.693365° (17 57 48.50, +04 41 36.1) | SIMBAD |
| Movimiento propio | −801.551, +10362.394 mas/año (**10.393″/año**, hacia el norte) | Gaia DR3 |
| Paralaje | 546.976 ± 0.040 mas (1.83 pc) | Gaia DR3 |
| Velocidad radial | −110.1 km/s | SIMBAD |
| Tipo | M4V | SIMBAD |
| Brillo (Vega) | G 8.19 · J 5.24 · H 4.83 · K 4.52 | SIMBAD / 2MASS |

## En SPHEREx

| Pasada | Fechas | Imágenes | Por detector (1–6) | Colección |
|---|---|---|---|---|
| 1 | 15 ago – 1 oct 2025 | 118 | 24 · 18 · 18 · 23 · 18 · 17 | DR1 |
| 2 | 11 mar – 5 may 2026 | 121 | 18 · 18 · 24 · 18 · 19 · 24 | DR1 |
| 3 | 16 ago – 22 sep 2026 | 120 | 18 · 25 · 17 · 18 · 24 · 18 | QR3 |

- **Dónde está en cada pasada** (cuenta propia, sin paralaje): ≈ 269.4463, +4.7673 (sep 2025) →
  269.4462, +4.7690 (abr 2026) → 269.4461, +4.7702 (sep 2026). Se mueve ~6.0″ entre la pasada 1 y la 2
  y ~4.3″ entre la 2 y la 3: **menos de un píxel por pasada**. El paralaje añade hasta 1.09″ entre
  pasadas opuestas.
- Dentro de una misma pasada de ~dos meses ya se corre ~1.7″ (≈ 0.3 px). (cuenta propia)
- **Orientación:** `SPS_EPA` = 180 en la pasada 1, 0 en la 2 y 180 en la 3. Según la definición del
  Supp., son de los barridos 2, 1 y 4, en ese orden. (cruce propio entre el Supp. §1.4 y los encabezados)
- **Saturación:** K = 4.52 Vega (≈ 6.4 AB) contra un inicio de no linealidad de 11.3 AB: cinco
  magnitudes de sobra. Núcleo con OVERFLOW y NaN, y halo BLOOM en las bandas cortas. (paso de Vega a AB:
  cuenta propia)
- **Comparar con WISE:** de 2010 (WISE) a 2026 (SPHEREx) Barnard se mueve ~166″, unos 27 píxeles de
  SPHEREx; desde 2MASS (~1998–2000), ~280″. (cuenta propia)

## Para el jurado (sin verificar)

Es la estrella con el mayor movimiento propio del cielo y el sistema más cercano al Sol después de Alfa
Centauri; en 2024–2025 se le confirmaron cuatro planetas pequeños (González Hernández et al. 2024; Basant
et al. 2025). **Comprobar antes de decirlo.**

## Fuentes

- Gaia DR3, archivo de la ESA: https://gea.esac.esa.int/archive/ (Gaia Collaboration, Vallenari et al. 2023, A&A 674, A1)
- SIMBAD, espejo de Harvard: https://simbad.cfa.harvard.edu/simbad/sim-id?Ident=Barnard%27s%20star (Wenger et al. 2000)
- SIA de IRSA (`spherex_dr1`, `spherex_qr3`), 13 nov 2026.
- *SPHEREx Explanatory Supplement* v2.1, Tabla 25 (saturación) y §1.4 (barridos).
