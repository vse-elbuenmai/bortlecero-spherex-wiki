# Cómo observa SPHEREx

Cómo barre el cielo, por qué cada foto ve otro color, por qué a veces la zona sale girada 180° y por
qué cada objeto tiene sus pasadas cuando las tiene. Verificado contra el Explanatory Supplement v2.1
(«Supp.», 10 nov 2026) y el paper de la misión.

## Cómo barre el cielo

En cada vuelta (~98 min) fotografía una tira que da la vuelta completa al cielo, a ~90° del Sol. Como
la Tierra avanza alrededor del Sol, esa tira se va corriendo: **en seis meses pasa por todo el cielo**.
Una zona dada se completa en pocos días, y un objeto típico queda medido en sus 102 colores en unas dos
semanas. [Caltech, Survey; Bock et al. 2026 §IV.2]

Analogía de astrofotografía: un mosaico enorme con un filtro distinto en cada panel. Para tener un
objeto en todos los colores hay que mover el campo de modo que el objeto pase por todas las franjas.

## Cómo sale un espectro de una cámara sin rendija

1. Cada detector tiene encima un filtro cuyo color **cambia de un borde al otro** (LVF), en 17 franjas
   o canales.
2. Una exposición mide **un solo color** de cada objeto: el de la franja donde cayó.
3. La nave se mueve un poco, el objeto cae en otra franja y se mide otro color.
4. Juntando las exposiciones de unos días se tiene el espectro completo.

Un **grupo de apuntados** son 17 fotos a la misma longitud eclíptica, separadas un canal en latitud.
[Supp. §1.4]

**Consecuencia para el reto:** dos fotos del mismo objeto casi nunca ven el mismo color. Ver
[trampas.md](../trampas.md), trampa 2.

## Pasada no es lo mismo que foto

En cada pasada SPHEREx fotografía el mismo lugar **unas cien veces**, una en cada color: la Estrella de
Barnard tiene 359 archivos en 3 pasadas (≈ 120 por pasada). Cada pasada dura de días a unos dos meses
según el objeto. [SIA de IRSA, 13 nov] (cuenta propia)

## El giro de 180°

- La nave siempre alinea el lado largo de su campo con las líneas de latitud eclíptica. Para que el
  panel solar reciba luz, en la mitad **ascendente** de la órbita va con ángulo de posición eclíptico
  **PA = 0** y en la **descendente** con **PA = 180**. [Supp. §1.4]
- Cada zona del cielo se visita más o menos cada seis meses, **alternando la orientación**.
- **Cómo saberlo en cada archivo:** el encabezado trae `SPS_EPA` (0 o 180). El Supp. lo llama
  «SPS PA ECL».

## Los cuatro barridos

Los barridos se definen por la orientación, no por el calendario: [Supp. §1.4 y §2.2]

| Barrido | Cuándo | Orientación |
|---|---|---|
| 1 | primeros 12.5 meses (1 may 2025 – ~16 may 2026) | PA = 0 |
| 2 | primeros 12.5 meses | PA = 180 |
| 3 | segundos 12.5 meses (~16 may 2026 – ~jun 2027) | PA = 0 |
| 4 | segundos 12.5 meses | PA = 180 |

- **Los barridos 3 y 4 van corridos medio canal** (unos **6′** en el cielo) respecto a los 1 y 2. Así,
  al juntar la misión completa, cada espectro queda muestreado al doble de fino. Una pasada del segundo
  año nunca repite exactamente los colores del primero: lo más cercano queda a medio canal. [Supp. §2.2]
- Con `SPS_EPA` y la fecha se sabe a qué barrido pertenece una foto.
- El «primer mapa de todo el cielo» que la NASA anunció el 18 dic 2025 es la primera cobertura completa
  (seis meses), que mezcla las dos orientaciones. No equivale al barrido 1.

## Por qué cada objeto tiene sus pasadas cuando las tiene

SPHEREx mira siempre a ~90° del Sol, así que ve cada zona cuando el Sol está a un cuarto de vuelta de
ella: dos veces al año, con seis meses de diferencia. Cuanto más cerca de un polo eclíptico está un
objeto, más dura cada ventana. Por eso R Draconis (latitud eclíptica +81°) se observa casi todo el año y
RW Aurigae (+8°) apenas dos o tres semanas por pasada. (cuenta propia, a partir del Supp. §1.4)

Mirar a ~90° del Sol también es mirar justo donde el **paralaje** es máximo, y seis meses después se ve
por el lado contrario: entre dos pasadas opuestas una estrella cercana se corre, además de su
movimiento propio, hasta 2 × su paralaje (1.09″ para Barnard). (cuenta propia)

## Los campos profundos

Dos zonas de ~100 grados cuadrados cerca de los polos eclípticos se observan casi en cada vuelta: más
de 400 observaciones por canal en el centro. El del sur está corrido para evitar las Nubes de
Magallanes. [Bock et al. 2026 §IV.2.5] De los cinco objetos de prueba, sólo **R Draconis** cae en un
campo profundo (en su borde), y sus imágenes están en las colecciones `_deep`
([datos/como-llegar.md](../datos/como-llegar.md)).

## Fuentes

- *SPHEREx Explanatory Supplement* v2.1, §1.4 y §2.2: https://irsa.ipac.caltech.edu/data/SPHEREx/docs/SPHEREx_Expsupp.pdf
- Caltech, Survey: https://spherex.caltech.edu/page/survey
- Bock et al. 2026, ApJ 999, 139 — https://arxiv.org/abs/2511.02985
- SIA de IRSA, consultas del 13 nov 2026 (conteos por objeto en [objetos/](../objetos/README.md)).
