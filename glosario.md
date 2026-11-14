# Glosario

Las palabras que salen todo el tiempo, en simple y con una analogía de desarrollo web o de
astrofotografía cuando ayuda. Orden alfabético.

**AB / Vega (magnitudes).** Dos escalas para medir brillo. Son logarítmicas y al revés: **más chico =
más brillante**; 5 magnitudes = 100 veces. Para pasar de Vega a AB se suma una constante por banda (J
+0.91, H +1.39, K +1.85, W2 +3.34). Los límites de SPHEREx están en AB.

**Apilar (stack, coadd).** Sumar varias fotos del mismo campo para sacar señal débil, como apilar
subexposiciones en astrofotografía. **Shift and add** es apilar moviendo cada foto según una velocidad
supuesta, para que algo que se mueve sume en el mismo punto.

**Banda / detector / canal.** SPHEREx tiene 6 detectores, y cada uno es una **banda** (1 a 6). Cada
banda se divide en 17 **canales** (colores). 6 × 17 = 102.

**Banderas (FLAGS).** Una máscara de bits por píxel: cada bit es un aviso (rayo cósmico, saturado,
fantasma…). Como un campo `flags` en una tabla donde se guardan varios booleanos en un entero.

**Barrido (survey) / pasada (visita).** Un **barrido** es una cobertura de todo el cielo con una
orientación (hay 4 en la misión). Una **pasada** es la ventana de días o semanas en que SPHEREx ve un
objeto dado; en cada una lo fotografía ~100 veces.

**Campo profundo.** Zonas cerca de los polos eclípticos que SPHEREx mira casi en cada vuelta.

**CORS.** La regla del navegador que decide si una página puede pedir datos a otro dominio. Si un
servicio no manda la cabecera `Access-Control-Allow-Origin`, una página web no puede leer su respuesta.

**Cubo.** Una imagen con una tercera dimensión de color: x, y y longitud de onda.

**Época.** La fecha a la que se refiere una posición de catálogo (Gaia DR3: 2016.0). Como un valor en
caché con su timestamp: para usarlo hoy, hay que «actualizarlo» con el movimiento propio.

**Eclíptica.** El plano de la órbita de la Tierra proyectado en el cielo. SPHEREx organiza su barrido en
coordenadas eclípticas (longitud y latitud eclíptica).

**Enana marrón.** Un objeto entre estrella y planeta: no tiene masa para encender su núcleo, así que se
enfría con los años. Las más frías (tipo Y, como WISE 0855) casi no emiten luz visible: se ven en
infrarrojo.

**FITS.** El formato de archivo estándar de la astronomía. Un archivo trae varias **hojas** (HDU), cada
una con su encabezado y sus datos, como un libro de Excel con varias pestañas.

**Encabezado (header).** Pares clave–valor al inicio de cada hoja FITS: fecha, detector, orientación,
WCS… Como las cabeceras de una respuesta HTTP.

**HEALPix.** Una forma de dividir la esfera del cielo en pedazos de igual área. Es la cuadrícula de los
HiPS y del cubo de SPHEREx.

**HiPS.** Imágenes del cielo cortadas en mosaicos por nivel de zoom, como los tiles de un mapa web
(XYZ). Un visor como Aladin Lite pide sólo los mosaicos que se ven.

**Luz zodiacal.** Luz del Sol reflejada por el polvo del sistema solar. Es un fondo que cubre todo,
parecido a la contaminación lumínica en astrofotografía. SPHEREx la entrega como modelo aparte (ZODI) y
no la resta de la imagen.

**LVF (filtro lineal variable).** Un filtro cuyo color cambia de un borde al otro. Por eso cada foto de
SPHEREx ve otro color según dónde cayó el objeto.

**Mira.** Gigante roja que pulsa con un periodo de meses (R Draconis: 245.6 días) y cambia mucho de
brillo.

**MJD.** *Modified Julian Date*: fecha como número de días, cómoda para restar fechas. Como un timestamp
Unix, pero en días.

**MJy/sr.** Unidad de brillo por área de cielo (megajansky por estereorradián). La que traen las
imágenes de SPHEREx.

**Movimiento propio.** Cuánto se desplaza una estrella en el cielo por año, en ″/año o mas/año. Barnard:
10.4″/año, el mayor del cielo.

**mas.** Milisegundo de arco: 1/1000 de segundo de arco.

**Nivel 2 (L2).** Las imágenes ya calibradas, una por detector y por exposición. Es lo que entrega
SPHEREx hoy.

**PA (ángulo de posición).** Hacia dónde está girada la cámara respecto al norte (o, en SPHEREx, a la
eclíptica). `SPS_EPA` = 0 o 180.

**Paralaje.** El vaivén aparente de una estrella cercana porque la Tierra (y SPHEREx con ella) da la
vuelta al Sol. Como ver un dedo con un ojo y luego con el otro. Distancia en pársecs = 1 / paralaje en
segundos de arco.

**Pársec (pc).** 3.26 años luz. **UA:** la distancia Tierra–Sol.

**PSF / ePSF.** Cómo se ve un punto de luz en la imagen: el «kernel de desenfoque» del telescopio.
**FWHM** es su ancho a media altura.

**QR / DR.** *Quick Release* (entrega rápida) y *Data Release* (entrega reprocesada y definitiva). Hoy
están vigentes DR1 y QR3.

**RA / Dec.** Ascensión recta y declinación: la longitud y latitud del cielo. En este wiki, en grados
(ICRS).

**Recorte (cutout).** Un pedazo de una imagen alrededor de un punto, servido por IRSA.

**Reproyectar.** Remuestrear una imagen sobre otra cuadrícula del cielo (otra orientación, otra
escala). Como normalizar dos capturas al mismo viewport y rotación antes de compararlas.

**RUWE.** Indicador de Gaia de qué tan bien se ajustó una estrella como punto simple; mayor que ~1.4
suele indicar algo raro, como una doble.

**Saturación / OVERFLOW / no lineal.** El píxel se llenó: como las altas luces quemadas en una foto.
Antes de llenarse del todo, la respuesta deja de ser proporcional (no lineal).

**Segundo de arco (″).** 1/3600 de grado. El píxel de SPHEREx mide 6.15″.

**SIA.** *Simple Image Access*: un servicio de búsqueda por posición. Le das RA, Dec y un radio, y te
devuelve una tabla con las imágenes que cubren ese punto.

**SIMBAD / Sesame / VizieR.** Servicios del CDS: base de datos de objetos, conversor de nombre a
coordenadas, y catálogos. Hoy se usan sus espejos de Harvard.

**SIP.** Polinomios en el encabezado que corrigen la distorsión de la óptica. El WCS de SPHEREx se lee
con SIP.

**SWIR / MWIR.** Infrarrojo de onda corta (bandas 1–3) y media (bandas 4–6).

**T Tauri.** Estrella muy joven, todavía rodeada de gas y polvo; cambia de brillo de forma irregular
(RW Aurigae).

**TAP / ADQL.** Consultas tipo SQL a un archivo astronómico por HTTP. ADQL es el dialecto de SQL.

**UTC.** Las fechas de los archivos van en UTC; Guadalajara es UTC−6.

**WCS.** *World Coordinate System*: las fórmulas del encabezado que convierten un píxel (x, y) en una
posición del cielo (RA, Dec). Como una matriz de transformación de CSS, más la distorsión SIP.
