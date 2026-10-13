# celinki.com — plan responsive (celular primero, WhatsApp primero)

Fecha: 2026-10-12. Supuesto: la mayoría de las visitas y ventas llegan desde celular (volante con QR, WhatsApp, Facebook). Todo se diseña primero para una pantalla de 360–430 px y luego se amplía.

## 1. Principios
- **WhatsApp siempre a un toque**, pero sin sacar a la persona antes de ver precios: barra inferior fija con WhatsApp desde que se pasa la parte de arriba.
- **Una columna**, textos cortos, botones grandes (mínimo 48 px de alto), nada de tablas anchas.
- **Ligera**: la página debe abrir rápido con datos móviles en un celular de gama baja.
- **Probar en celular real** (Android de gama baja y iPhone) antes de dar por terminado cada paso.

## 2. Por sección

### Barra superior
- [x] En celular: logo a la izquierda y botón «WhatsApp» a la derecha; el menú de texto se oculta (hoy ya se oculta).
- [ ] Botón ☰ opcional con Micas · Cómo pedir · Entregas · Cortadoras · Tienda, si al probar hace falta.
- [x] Altura máxima 56 px para no robar pantalla.

### Parte de arriba (hero)
- [x] Orden en celular: título → frase de corte → bloque «Entrega gratis» → botones → foto de la cortadora (abajo o más chica).
- [x] Título 32–36 px; bloque de entrega a lo ancho con los íconos de Pachuca y Mineral de la Reforma en una sola línea si caben.
- [x] Botones uno debajo del otro, a lo ancho.
- [ ] Que el bloque de entrega gratis se vea sin hacer scroll en un celular de 360 × 740.

### Micas (celular y tablet)
- [x] 2 columnas en celular (no 1): foto cuadrada, nombre, precio grande; la descripción se puede cortar a una línea.
- [ ] Alternativa a probar: carrusel horizontal deslizable por categoría (Celular / Tablet) con `scroll-snap`.
- [ ] Ícono de carga hecho (`public/img/cargando.svg`); falta: fotos de máximo ~60 KB en celular (WebP, `srcset` 300/600 px).

### Cómo pedir
- [x] Pasos en 1 columna con la ilustración más chica a la izquierda y el texto a la derecha (tarjeta horizontal), para que los 4 pasos quepan en ~1.5 pantallas.
- [x] Botones «Pedir cortadas a mi modelo» y «Pedir lámina sin corte» a lo ancho, uno debajo del otro.

### Cortadoras
- [x] 1 columna, foto a lo ancho; o mostrar 4 y botón «Ver todas las cortadoras (19)».
- [x] Recuadro del paquete y condiciones (2–3 semanas, 60% de anticipo) arriba, compacto.

### Recoge en tienda
- [x] Datos arriba y mapa abajo de 220 px de alto; «Cómo llegar» a lo ancho.

### Pie
- [x] WhatsApp, zonas de entrega con íconos y horario; espacio extra abajo para que la barra fija no tape nada.

## 3. WhatsApp primero
- [x] **Barra inferior fija en celular** (reemplaza la píldora flotante): «💬 Pedir por WhatsApp · 771 868 2542», aparece después de pasar la parte de arriba.
- [x] Mensajes prellenados claros: cortadas («modelos y cantidades:») o lámina sin corte («cantidad:»).
- [x] Usar `https://wa.me/52…` (abre la app directo en celular).
- [ ] Respuesta rápida en WhatsApp Business: catálogo, precios y mínimo para entrega gratis, para contestar en segundos.
- [ ] Medir clics a WhatsApp por botón (cuando haya analítica) para saber cuál funciona.

## 4. Rendimiento en celular
- [ ] Imágenes en WebP con `srcset` y `sizes`; `loading="lazy"` en todo lo que no esté en la primera pantalla.
- [x] Foto del hero con `fetchpriority="high"` y tamaño fijo (sin saltos al cargar).
- [x] Mapa de Google cargado solo al llegar a la sección (ya tiene `loading="lazy"`).
- [ ] Meta: Lighthouse móvil ≥ 90 en rendimiento y accesibilidad.

## 5. Cómo probar
- [ ] Chrome DevTools: 360×740 (Android chico), 390×844 (iPhone), 768×1024 (tablet).
- [ ] Celular real con datos móviles (no wifi).
- [ ] Escanear el QR del volante y revisar que abra bien y rápido.

## Orden sugerido
1. Barra inferior de WhatsApp + hero en celular.
2. Micas en 2 columnas + imágenes WebP.
3. Cómo pedir en tarjetas horizontales.
4. Cortadoras compactas, tienda y pie.
5. Medición y ajustes con celular real.

## Avance 2026-10-13
Vista de celular publicada: barra fija de WhatsApp (aparece al pasar la parte de arriba), hero compacto con botones a lo ancho, micas en 2 columnas, «Cómo pedir» en tarjetas horizontales, cortadoras con «Ver todas (19)», tienda con mapa de 220 px y pie con zonas. Falta: WebP/srcset, carrusel opcional, menú ☰ si hace falta, prueba en celular real y medición.
