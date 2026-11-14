# Las trampas

Lo que hace que un parpadeo ingenuo (poner las fotos una tras otra, tal cual) muestre cosas que no
pasaron o esconda las que sí. Cada trampa dice **qué pasa**, **por qué** y **cómo se nota en los
datos**. Cómo resolverlas lo decide el equipo. Verificado contra el Explanatory Supplement v2.1
(«Supp.») y los datos reales del 13 nov 2026.

## 1. La zona sale girada 180° entre pasadas

- **Qué pasa:** dos fotos del mismo lugar tomadas con seis meses de diferencia tienen el cielo girado
  media vuelta. Puestas tal cual una tras otra, todo el campo brinca.
- **Por qué:** la nave vuela con PA = 0 en la mitad ascendente de la órbita y con PA = 180 en la
  descendente, para que el panel solar reciba luz. [Supp. §1.4]
- **Cómo se nota:** la clave `SPS_EPA` del encabezado (0 o 180). Las tres pasadas de Barnard son 180, 0
  y 180.

Más en [spherex/como-observa.md](spherex/como-observa.md).

## 2. Cada foto ve otro color

- **Qué pasa:** un cambio de brillo entre dos fotos no prueba que la estrella haya cambiado.
- **Por qué:** el filtro cambia de color de un borde al otro del detector, y la estrella cae en otra
  franja en cada foto. Además, los barridos 3 y 4 van corridos medio canal, así que una pasada del segundo
  año nunca repite exactamente los colores del primero. [Supp. §1.4 y §2.2]
- **Cómo se nota:** la hoja WCS-WAVE (o el producto Spectral WCS) dice qué longitud de onda vio cada
  píxel. El SIA sólo dice el detector, no el canal.
- **Ojo:** es una trampa de **brillo**, no de **posición**: la estrella está en el mismo lugar la
  fotografíe en el color que la fotografíe.

## 3. Saturación

- **Qué pasa:** el centro de las estrellas brillantes no tiene un valor fiable: queda en NaN o en zona no
  lineal, con un halo marcado.
- **Por qué:** OVERFLOW se activa a la mitad del pozo lleno; si pasa en los primeros segundos de la
  exposición, el píxel queda en NaN. [Supp. Tabla 16]
- **Quién:** Barnard satura en todas las bandas (núcleo NaN, halo BLOOM); R Draconis satura siempre (siete
  magnitudes de sobra); RW Aurigae cae en zona no lineal; WISE 0855 es muy débil. **Epsilon Indi B es la
  única limpia.** Límites por banda en [datos/el-archivo-fits.md](datos/el-archivo-fits.md#saturación).
- **Cómo se nota:** los bits OVERFLOW (1), NONLINEAR (15) y BLOOM (26) de FLAGS.

## 4. El movimiento es menor que un píxel

- **Qué pasa:** entre dos pasadas, la estrella que más se mueve del cielo se corre menos de un píxel.
- **Números:** Barnard ≈ 0.8 px por pasada y ≈ 1.9 px en toda la serie; Eps Indi B ≈ 1.1 px en 17 meses;
  WISE 0855 ≈ 1.4 px. (cuenta propia, sin paralaje) Dentro de una sola pasada de dos meses, Barnard ya se
  corre ~0.3 px.
- **Por qué:** el píxel de 6.15″ se eligió para cubrir el cielo rápido, no para ver cosas que se mueven.
- **A favor:** la astrometría de cada imagen es buena: RMS < 0.3″ (≈ 0.05 px) contra Gaia. [Supp. §4.2.2]

## 5. La coordenada de catálogo no es la de hoy

- **Qué pasa:** la posición de un catálogo es la de su **época** (Gaia DR3: 2016.0; WISE: ~2010; 2MASS:
  ~1998–2000), no la de la foto.
- **Por qué:** las estrellas cercanas se mueven. Hay que llevar la posición a la fecha de cada foto con
  su movimiento propio. Y el **paralaje pesa**: SPHEREx mira a ~90° del Sol, donde el paralaje es máximo,
  y seis meses después lo ve del otro lado. Entre pasadas opuestas suma hasta 2 × paralaje: **1.09″** en
  Barnard, 0.88″ en WISE 0855 y 0.54″ en Eps Indi B. Es más que el error de posición (0.3″), así que se
  nota. (cuenta propia)
- **Cómo lo hace el pipeline:** ya aplica el movimiento propio de Gaia a la fecha de cada imagen en la
  astrometría y en la máscara SOURCE. [Supp. §3.2.8 y Tabla 4] Los profesionales hacen lo mismo:
  Rustamkulov et al. 2026 usaron posiciones corregidas por movimiento propio.

## 6. WISE 0855 no está donde dice el enunciado

- Las coordenadas del enunciado son de **~2010**. Hoy está **≈ 133.760, −7.2422**: unos 125″ al oeste,
  ~20 píxeles. Un recorte chico centrado en el enunciado no la contiene.
- A **29″** de esas coordenadas hay una fuente **fija**, igual de brillante en 4.6 µm, fácil de confundir
  con ella.
- Sólo se detecta por encima de **3.9 µm**: bandas 5 y 6.
- No tiene imágenes en QR3: todo está en DR1.

Detalle en [objetos/wise-0855.md](objetos/wise-0855.md).

## Otras que muerden

- **El fondo no es plano.** IMAGE no trae restada la luz zodiacal (viene aparte, en ZODI) ni las líneas
  de la atmósfera (helio a 1.083 µm, auroras). [Supp. §2.2 y §3.1] Como el color cambia a lo largo del
  detector, el fondo cambia por franja. (observado en datos reales; sin cita)
- **En las bandas cortas una estrella mide ~1 píxel** (PSF < 3″ contra píxel de 6.15″): un filtro de
  «quitar puntitos» por forma se come estrellas reales. Los defectos se reconocen por FLAGS.
- **La distorsión llega a más de 10 píxeles en las esquinas.** El WCS se lee con SIP. [Supp. §4.2.2]
- **Hay imágenes malas.** `FINAST` mayor que 1 = astrometría que no sirve; y hay una
  [lista pública de imágenes muy contaminadas](https://spherex.caltech.edu/page/anomalyimages).
- **Eps Indi A, saturadísima, está a 6.7′ de B y se mueve igual.** En el campo de B hay dos cosas que se
  desplazan juntas.
- **Las fechas de los archivos están en UTC.** El lanzamiento fue el 11 mar 2025 en California y el
  12 mar en UTC.
- **No mezclar QR2 con QR3**: otra calibración de ganancia. Con DR1 + QR3 no hace falta. [Supp. §2.1]
- **El cubo de todo el cielo es un promedio**: no sirve para ver cambios en el tiempo
  ([datos/cubo-de-todo-el-cielo.md](datos/cubo-de-todo-el-cielo.md)).
- **CDS está caído** ⏳: SIMBAD, VizieR, Sesame y `aladin.js` desde su servidor. Hay espejos
  ([servicios.md](servicios.md)).

## Fuentes

- *SPHEREx Explanatory Supplement* v2.1 (10 nov 2026): https://irsa.ipac.caltech.edu/data/SPHEREx/docs/SPHEREx_Expsupp.pdf
- Rustamkulov et al. 2026, ApJ 1009, 185 — https://arxiv.org/abs/2607.00543
- Gaia DR3 y SIMBAD (fichas en [objetos/](objetos/README.md)); SIA de IRSA, 13 nov 2026.
