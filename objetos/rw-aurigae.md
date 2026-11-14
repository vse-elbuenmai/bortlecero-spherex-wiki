# RW Aurigae

Objeto de prueba de **cambio de brillo**. Verificado el 13 nov 2026 (SIMBAD en Harvard, Gaia DR3 en la
ESA, GCVS por el VizieR de Harvard, SIA de IRSA).

| Dato | Valor | Fuente |
|---|---|---|
| Qué es | estrella joven (T Tauri) doble: A + B | SIMBAD (`TT*`, K1/5e + K5e) |
| Posición J2000 | 76.956526°, +30.401438° (05 07 49.57, +30 24 05.2) | SIMBAD |
| RW Aur A | Gaia DR3 `156430822114424576` · G 12.18 · pm +2.64, −27.40 mas/año · paralaje 6.406 mas | ESA |
| RW Aur B | Gaia DR3 `156430817820015232` · G 13.04 · RUWE 16.4 | ESA |
| Separación A–B | **1.5″**: menos de un píxel (cuenta propia con Gaia DR3) | Gaia DR3 |
| Brillo (Vega), las dos juntas | J 8.38 · H 7.62 · K 7.02 | SIMBAD / 2MASS |
| Variabilidad | tipo IT (irregular, T Tauri); V entre 9.2 y 12.5 | GCVS |

## En SPHEREx

| Pasada | Fechas | Imágenes | Por detector (1–6) | Colección |
|---|---|---|---|---|
| 1 | 1 – 20 sep 2025 | 112 | 19 · 18 · 19 · 19 · 18 · 19 | DR1 |
| 2 | 20 feb – 12 mar 2026 | 114 | 19 · 19 · 19 · 19 · 19 · 19 | DR1 |
| 3 | 2 – 16 sep 2026 | 110 | 18 · 19 · 18 · 18 · 19 · 18 | QR3 |

- **Tres puntos en el tiempo**, cada uno de dos o tres semanas, separados medio año. No hay cobertura
  entre pasadas: lo que haya hecho la estrella en medio no se ve.
- **Saturación:** K = 7.02 Vega (≈ 8.9 AB), unas 2.4 magnitudes por encima del inicio de no linealidad
  (cuenta propia). El núcleo no sirve para medir; SPHEREx ve A y B como un solo punto.
- **La trampa del color pega de lleno aquí:** cada foto la ve en otra longitud de onda. Un cambio entre
  dos fotos sueltas no prueba nada ([trampas.md](../trampas.md), trampa 2).
- Para saber cómo estaba en visible en cada pasada: curva de luz de la AAVSO
  (https://www.aavso.org/LCGv2/, objeto «RW Aur»). La AAVSO no es de la NASA: si se usa, va en «otras
  referencias».

## Para el jurado (sin verificar)

RW Aur A tiene apagones profundos y largos (de hasta 2–3 magnitudes en visible; los más conocidos en
2010–2011 y desde 2014), que se atribuyen a polvo que tapa la estrella, quizá levantado por el paso
cercano de B. En infrarrojo el efecto es distinto que en visible (Rodriguez et al. 2013 y 2016; Günther
et al. 2018). **Comprobar antes de decirlo.**

## Fuentes

- SIMBAD, espejo de Harvard: https://simbad.cfa.harvard.edu/simbad/sim-id?Ident=RW%20Aur (Wenger et al. 2000)
- Gaia DR3, archivo de la ESA: https://gea.esac.esa.int/archive/ (Gaia Collaboration, Vallenari et al. 2023)
- GCVS (Samus et al. 2017), por https://vizier.cfa.harvard.edu
- SIA de IRSA (`spherex_dr1`, `spherex_qr3`), 13 nov 2026.
