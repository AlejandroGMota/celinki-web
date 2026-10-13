# celinki.com — plan visual

Fecha: 2026-10-12. Basado en capturas de la página publicada. Objetivo: que en 5 segundos quede claro **(1) te las vendemos cortadas a tu modelo, mismo precio** y **(2) entrega gratis en Pachuca y Mineral de la Reforma**.

## 1. Revisión crítica de lo que hay hoy

| Problema | Por qué importa |
|---|---|
| No hay barra superior, logo ni favicon; la página empieza con una tarjeta flotante | Se ve como borrador, no como proveedor serio |
| El servicio de corte está en un recuadro punteado chico, debajo del subtítulo | Es el diferenciador principal y casi no se ve |
| «Entrega gratis en Pachuca y Mineral de la Reforma» es una línea de texto corrido | Lo segundo más importante se pierde entre otros datos |
| Hay un solo botón y está en la primera tarjeta; las tarjetas de producto dicen «Pedir» sin decir si cortada o lámina | El cliente no sabe qué está pidiendo |
| La foto del hero (cajas HD y Mate) es igual a las de las tarjetas | No cuenta nada nuevo: ni el corte, ni la entrega |
| Cuadrículas con huecos: «Privacidad HD» y «360» solas en su fila; igual «Tablet 13" Privacidad HD» | Se ve desordenado |
| Recuadros en blanco mientras cargan las fotos | Parece que la página está rota |
| Mezcla de estilos: fotos KASR, dos ilustraciones propias (Blue Ray, 13" privacidad) | Bien por ahora; a futuro, fotos propias |
| Sin preguntas frecuentes ni señales de confianza (tiempo de entrega, cómo se paga, garantía) | Un vendedor nuevo no se anima a pedir |

## 2. Estructura nueva (de arriba hacia abajo)

1. **Barra superior fija** (blanca, delgada): logo Celinki · enlaces «Láminas · Cortadas · Entregas · Cortadoras» · botón WhatsApp verde.
2. **Hero a todo lo ancho, dos mensajes grandes:**
   - Título: «Micas de hidrogel **cortadas a tu modelo**».
   - Subtítulo: «O lámina a mayoreo. Mismo precio.»
   - Dos sellos grandes uno junto al otro:
     - ✂ **Cortada a tu modelo · mismo precio**
     - 🚚 **Entrega gratis** · 50 piezas o 30 de privacidad
   - Botones: «Pedir cortadas» (verde, principal) y «Pedir lámina» (blanco con borde).
   - Imagen: video corto o foto del cortadora KASR cortando una mica, con un celular al lado (de `docs/referencias/kasr/videos/`).
4. **Sección «Entregas gratis»** (bloque propio, fondo verde muy claro):
   - Viñetas con ícono de cada lugar:
     - ![](../public/img/iconos/pachuca-reloj.svg) **Pachuca** · Reloj Monumental
     - ![](../public/img/iconos/mineral-castillete.svg) **Mineral de la Reforma** · castillete minero
   - Condición en grande: «desde **50 piezas** o **30 de privacidad**».
   - Mapita simple (SVG) con las dos zonas marcadas y GAMMA en Santa Gertrudis como punto de recolección.
5. **Catálogo de láminas** (como hoy, pulido):
   - Selector arriba: **Cortada / Lámina** (mismo precio; cambia el texto del botón y el mensaje de WhatsApp: «quiero 10 HD cortadas para iPhone 15» vs «quiero 10 láminas HD»).
   - Celular y Tablet en pestañas o con filtro, en vez de dos cuadrículas.
   - Tarjetas de la misma altura y cuadrícula sin huecos (4 columnas en computadora, 2 en celular, centrar la última fila).
   - Fondo gris claro en el recuadro de la foto mientras carga.
   - Etiqueta de privacidad («Nadie ve tu pantalla») en las 3 de privacidad.
6. **Cómo pedir** (debajo de las micas, arriba de las cortadoras; decidido 2026-10-12).
   6b. **Cortadoras KASR:** se quedan como están, con sus tamaños actuales (decidido 2026-10-12).
7. **Preguntas frecuentes:** ¿cuánto tarda la entrega?, ¿cómo pago?, ¿qué modelos cortan?, ¿cortan para tablet?, ¿qué pasa si la mica no queda?, ¿puedo recoger en tienda?
8. **Recoge en tienda** (como quedó, con mapa).
9. **Pie:** logo, WhatsApp, zonas de entrega con sus íconos, horario.

## 3. Detalles visuales

### Íconos de lugar (viñetas)
Archivos en `public/img/iconos/`, 64×64, círculo de color con dibujo blanco; se usan como viñeta de 24–32 px en listas y pie.

| Lugar | Ícono | Por qué |
|---|---|---|
| Pachuca | **Reloj Monumental** (verde lima) | Es el símbolo más reconocido de Pachuca |
| Mineral de la Reforma | **Castillete minero** (dorado) | El municipio debe su nombre a la minería; el castillete es el símbolo minero de la región |

Alternativas si no convencen: Pachuca → Cristo Rey o el escudo de los Tuzos; Mineral de la Reforma → la parroquia de Pachuquilla.

### Sellos de servicio
- Forma de píldora grande, ícono a la izquierda, dos líneas de texto.
- ✂ Cortada a tu modelo → fondo negro, texto blanco, tijeras verdes.
- 🚚 Entrega gratis → fondo verde lima, texto negro, con los dos íconos de lugar pequeños al final.

### Colores y tipografía (se mantienen)
- KASR: blanco, gris claro `#f5f6f8`, verde lima `#8dc63f`, dorado `#b8893a`, negro `#1b1b1f`.
- Títulos en serif (como el empaque KASR), texto en Montserrat.

### Movimiento (del checklist, sección 9)
- Aparición suave al hacer scroll en tarjetas y pasos.
- Los dos sellos del hero entran con un pequeño rebote al cargar.
- Video de la cortadora en bucle, sin sonido, con foto de respaldo.
- Todo quieto si el teléfono tiene «reducir movimiento».

### Celular primero
- Hero apilado: título → sellos → botones → imagen.
- Botón de WhatsApp fijo abajo a lo ancho («Pedir por WhatsApp»), en vez de la píldora flotante.
- Pestañas Celular/Tablet deslizables.

## 4. Orden de trabajo sugerido
1. Barra superior + favicon (con el logo elegido).
2. Hero nuevo con los dos sellos y dos botones.
3. Sección «Entregas gratis» con los íconos de lugar.
4. Selector Cortada / Lámina en el catálogo + cuadrícula sin huecos + fondo de carga.
6. Preguntas frecuentes y pie.
7. Animaciones y video.

## Pendientes de ti
- Elegir logo (A, B o C de `docs/logo/propuestas.jpg`).
- ¿Cuánto tarda la entrega y qué días? (para el sello y las preguntas).
- ¿Cómo te pagan? (efectivo, transferencia).
- Fotos reales: tu cortadora cortando, micas colocadas, tus láminas Blue Ray y 13" privacidad.

## Volante imprimible (2026-10-12)
Para dejar en locales, en persona. **Sin precios** (puede leerlo un empleado, no el dueño); los precios se dan directo al dueño por WhatsApp.
- Archivos: `docs/volante/volante.html` (diseño) y `docs/volante/volante-carta-4.pdf` (listo para imprimir: carta, 4 por hoja, con líneas de corte).
- Contenido: logo, «Micas de hidrogel», cortadas al tamaño del modelo que elijas o en lámina sin corte, 8 tipos con foto, entrega gratis en Pachuca y Mineral de la Reforma (desde 50 piezas o 30 de privacidad), QR a `celinki.com/?utm_source=volante` y WhatsApp 771 868 2542.
- [ ] Imprimir prueba y revisar que el QR se lea con el celular
- [ ] Cambiar el logo provisional cuando se elija el definitivo (regenerar el PDF)
- [ ] Llevar volantes a locales de Pachuca y Mineral de la Reforma
- [ ] Contar visitas que llegan por el QR (parámetro `utm_source=volante`) cuando haya analítica
