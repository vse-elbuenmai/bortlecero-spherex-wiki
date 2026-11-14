# WiseView

El recurso que la NASA puso en el reto como «modelo o inspiración». Leído el 13 nov 2026: su página y el
README de su repositorio.

## Qué es

- «Wiseview is designed for quick visualization of moving objects in unWISE images.»
- Dirección: **http://byw.tools/wiseview** (sólo por http; por https rechaza la conexión).
- La opera el Museo Americano de Historia Natural (AMNH). Autores: **Dan Caselden y Paul Westin**.
- Código en **dominio público** (Unlicense): [backyardworlds/wiseview](https://github.com/backyardworlds/wiseview).
  Se puede leer, usar y adaptar, citándolo.
- Cita: Caselden et al. 2018, Astrophysics Source Code Library, ascl:1806.004.
- Datos: imágenes de **unWISE** arriba y de Pan-STARRS abajo, como referencia en visible.
- Hecha para Chrome. Sus enlaces a SIMBAD y VizieR apuntan a CDS, hoy caído.

## Lo que deja hacer

Controles de su panel, tal como aparecen:

- coordenadas en grados o sexagesimales; **campo de visión** en segundos de arco; zoom;
- banda W1, W2 o W1 + W2 en color (W2 al rojo, W1 al azul, el promedio al verde);
- **velocidad del parpadeo** (intervalo en ms);
- **ventana deslizante** en años: cuántas épocas se suman en cada cuadro, desde una por una hasta todo
  junto;
- valores mínimo y máximo, y **linealidad del estirado** (usa `astropy.visualization.AsinhStretch`);
  invertir la imagen; maximizar el rango dinámico;
- **separar direcciones de barrido** (WISE, como SPHEREx, ve cada zona desde dos lados de la órbita:
  separarlas resalta o cancela el paralaje);
- usar sólo NEOWISE; saltarse las épocas intermedias (antes contra después);
- **imagen de diferencia**, con una ventana de exclusión;
- **«shift and add»**: sumar las épocas siguiendo un movimiento propio que se escribe a mano;
- **superponer Gaia DR3**;
- objeto sintético (insertar o restar una fuente con posición, magnitud y movimiento dados);
- una leyenda de épocas con `+`, `-` y `.` (sumada, restada o sin usar) y un borde punteado cuando la
  animación vuelve a empezar, para no confundir el reinicio con un salto del objeto;
- clic para moverse; enlaces a SIMBAD, VizieR, Legacy Survey y a los sujetos de Zooniverse cercanos.

## Todo el estado va en la URL

Después de `#`: `ra`, `dec`, `size`, `band`, `speed`, `linear`, `mode`, `coadd_mode`, `zoom`… Por eso se
puede enlazar y embeber. El ejemplo de su README es justo WISE 0855:

`http://byw.tools/wiseview#ra=133.787&dec=-7.245150&size=120&band=2&speed=274&trimbright=521.66&linear=1&color=gray&mode=fixed&coadd_mode=time-resolved&zoom=12`

## Relación con el reto

Varias «consideraciones» del enunciado (sumar y restar fechas, elegir el campo, superponer Gaia, las
coordenadas en la URL) son funciones que WiseView ya tiene sobre WISE. Lo que WISE no tenía y SPHEREx sí:
los 102 colores.

**Diferencias de los datos** (hechos, no recomendaciones): WISE tiene píxel de 2.75″ y nitidez de ~6″ en
W1 y W2; SPHEREx, píxel de 6.15″. WISE cubre 2010–2024; SPHEREx empieza en 2025. W1 (3.4 µm) y W2
(4.6 µm) caen en las bandas 4 y 6 de SPHEREx. [WISE Explanatory Supplement §I.1]

## Fuentes

- WiseView: http://byw.tools/wiseview · código: https://github.com/backyardworlds/wiseview
- Caselden et al. 2018, ascl:1806.004
- unWISE: Lang 2014, AJ 147, 108; Meisner et al. 2017, AJ 153, 38 (los cita la página de WiseView)
- IPAC, WISE All-Sky Explanatory Supplement §I.1: https://wise2.ipac.caltech.edu/docs/release/allsky/expsup/sec1_1.html
