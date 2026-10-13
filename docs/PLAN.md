# celinki.com — plan

Tienda en línea de Celinki: accesorios para celular al menudeo, con envío a domicilio y recolección en el local GAMMA (Plaza Tere, Santa Gertrudis). La idea es un Buytiti, pero para cliente final.

Fecha: 2026-10-12. Estado: plan, sin código.

> **Alcance actual (2026-10-12): muestrario + pedido por WhatsApp. No se vende ni se cobra en línea.** El cliente ve el catálogo, arma su pedido y lo manda por WhatsApp; se cobra y entrega por fuera (en GAMMA o como se acuerde). Pagos en línea, envíos con guía y Cloud Functions quedan en la fase 3 («a futuro»), sin fecha.

> **Estado al 2026-10-13 (lee esto primero).** El plan cambió: celinki.com quedó como **sitio solo de hidrogel (Plan A)**, no como muestrario de accesorios. Lo que está publicado:
> - Hero con entrega gratis (Pachuca y Mineral de la Reforma, normalmente el mismo día), catálogo de micas para celular y tablet con precio por lámina, «Cómo pedir» ilustrado, cortadoras KASR (precio PDF + $2,500, entrega 2–3 semanas, anticipo 60%), preguntas frecuentes, recoger en GAMMA con mapa.
> - Vista de celular con barra fija de WhatsApp; ícono de carga en fotos.
> - SEO: robots.txt, sitemap, llms.txt, JSON-LD (LocalBusiness con catálogo + FAQPage), Open Graph, Search Console verificado.
> - WhatsApp único: 771 868 2542.
>
> Las secciones de abajo sobre accesorios, SmartLife, Firebase y fases 1–3 quedan como **historia**; lo vigente está en `PLAN-visual.md`, `PLAN-responsive.md`, `PLAN-seo.md` y `CHECKLIST-contenido.md`.

## 1. De dónde partimos

### SmartLife_Solutions (2023, `../SmartLife_Solutions`)
React 18 con Create React App, publicada en GitHub Pages. Tiene unas 950 líneas.

**Qué sirve:**
- La idea de las secciones por categoría: Fundas, Micas, Cargadores, Audífonos.
- Carrusel en el inicio y carrito flotante.
- Pedido por WhatsApp.
- Las fotos de `src/images/fundas/`.

**Qué no sirve:**
- Los productos están escritos dentro del código, cada categoría en su componente.
- Los precios están mezclados (pesos y dólares; hay fundas a 17.99).
- Create React App ya está descontinuado.
- Los estilos van en línea, y el carrito usa `localStorage` sin terminar.
- El número de WhatsApp es el anterior (527712384167).
- No hay pagos ni envíos.

**Conclusión:** se toma como referencia de secciones y del flujo, no como base de código. El repo nuevo empieza limpio.

### Accesorios-compras (`../Accesorios-compras`)
- Ya usa **Firebase**: Firestore, Auth con roles de admin y reglas de seguridad.
- Hace deploy a GitHub Pages con Actions.
- Ahí viven los productos, las listas y las ventas del local.
- `catalogo-buytiti/` y `catalogo-myshop/` tienen scrapers en Go y un `productos.json` con nombre, precio, stock, imagen y categoría. Sirven como modelo de catálogo y para comparar precios.

**Conclusión:** reutilizar el mismo proyecto de Firebase, o uno hermano, para el catálogo y los pedidos, y el mismo patrón de deploy.

### Buytiti, como referencia
Lo que hace bien y vale la pena copiar en minorista:
- catálogo grande por categorías y subcategorías;
- buscador;
- precio con oferta y precio original;
- stock visible;
- carrito y checkout con envío.

## 2. Qué queremos que se pueda hacer

**El cliente:**
1. Ve el catálogo por categoría (fundas, micas de cristal, privacidad e hidrogel, cargadores, cables, adaptadores, audio, etc.) y busca por modelo de celular.
2. Ve el precio, si hay existencia y las fotos.
3. Arma una lista de pedido y la manda por **WhatsApp** (7711030032) con el resumen: productos, cantidades, modelo de celular y si recoge en GAMMA o quiere envío.
4. El pago y la entrega se acuerdan por WhatsApp. *(A futuro: pagar en línea y recibir número de guía.)*

**Celinki (admin):**
- Da de alta productos y fotos, y ajusta precio y existencias (o «disponible / agotado»).
- *(A futuro: panel de pedidos con estados y guías, y reporte de ventas en línea.)*

**Información:**
- Páginas «Quiénes somos», «Ubicación y horario» (con el mapa de GAMMA), «Envíos y devoluciones», «Aviso de privacidad» y «Términos».
- Con solo muestrario basta un aviso de privacidad sencillo (por los datos que mande el cliente por WhatsApp); términos y devoluciones completos se vuelven obligatorios cuando se cobre en línea.

## 3. Tecnología propuesta

| Pieza | Propuesta | Por qué |
|---|---|---|
| Sitio | **Astro + TypeScript**, con islas de React para el carrito y el admin | El catálogo sale como HTML estático (rápido y bueno para Google). Encaja con GitHub Pages y reutiliza lo que ya sabes de React |
| Estilos | Tailwind CSS | Reemplaza los estilos en línea de SmartLife |
| Hosting | **GitHub Pages** con dominio celinki.com | Ya lo usas; gratis |
| Datos | **Firebase Firestore** (productos, pedidos) + **Firebase Storage** (fotos) | Ya lo usas en Accesorios-compras |
| Admin | Firebase Auth, con el patrón `admins/{uid}` que ya existe | Reutiliza auth.js y las reglas |
| Pedidos | Enlace `wa.me/527711030032?text=…` con el resumen de la lista | Sin servidor ni cobros |
| Analítica | Google Analytics 4 + Search Console | Saber qué buscan y de dónde llegan; contar clics a WhatsApp |
| *A futuro* | Mercado Pago Checkout Pro + Firebase Cloud Functions + Envia.com/Skydropx | Solo si se decide cobrar y enviar en línea (fase 3) |

**Costo fijo esperado:** solo el dominio, que ya está pagado. Firestore, Storage y Auth en plan gratuito alcanzan para un muestrario; no hace falta el plan Blaze mientras no haya Cloud Functions.

## 4. Fases

### Fase 0 — Dominio y esqueleto (1–2 días)
- [x] Crear el repo `celinki-web` en GitHub (público, para Pages gratis). (2026-10-12)
- [x] Astro con una portada sencilla: Celinki, qué vendemos, micas de hidrogel a mayoreo (entrega en Pachuca y Mineral de la Reforma), ubicación de GAMMA, horario y botón de WhatsApp (7711030032). Tailwind queda para la fase 1. (2026-10-12)
- [x] Archivo `CNAME` con `celinki.com` y deploy con GitHub Actions; Pages con fuente «GitHub Actions» y dominio celinki.com. (2026-10-12)
- [x] Verificar `celinki.com` en GitHub (registro TXT `_github-pages-challenge-AlejandroGMota`) **antes** de apuntar el DNS. Así nadie más puede usar el dominio en su propio Pages. (2026-10-12)
- [x] DNS en Namecheap (ver sección 5): 4 registros A y www → alejandrogmota.github.io; se quitó la página de estacionamiento y el reenvío de correo sigue igual. (2026-10-12)
- [ ] HTTPS forzado («Enforce HTTPS» en el repo, cuando GitHub emita el certificado).

### Fase 1 — Muestrario y pedido por WhatsApp (1 semana)
- [ ] Modelo de producto en Firestore: `productos/{id}` con nombre, slug, categoría, subcategorías, modelos compatibles, precio, precio original, disponible/agotado, fotos y estado activo.
- [ ] Páginas de categoría, de producto y buscador por modelo de celular.
- [ ] Lista de pedido en el navegador; botón «Pedir por WhatsApp» con el resumen (y botón directo en cada producto).
- [ ] Opción de recoger en GAMMA o pedir envío (se acuerda por WhatsApp).
- [ ] Admin: alta y edición de productos y fotos.
- [ ] Cargar el catálogo inicial: lo que hoy se vende en el local, con las fotos de SmartLife que sigan vigentes.
- [ ] Aviso de privacidad sencillo.

### Fase 2 — Crecimiento del muestrario
- [ ] Ofertas y productos destacados.
- [ ] SEO por modelo («funda iPhone 16 Pro», «mica privacidad Galaxy A55»).
- [ ] Ligar con el perfil de Google de GAMMA: sitio web, productos y publicaciones.
- [ ] Mostrar disponibilidad según lo que hay en el local (Accesorios-compras).
- [ ] Medir clics a WhatsApp por producto para saber qué se pide.

### Fase 3 — A futuro, sin fecha: vender en línea
Solo si se decide cobrar y enviar en línea:
- Mercado Pago Checkout Pro (tarjeta, OXXO, transferencia) con Cloud Functions para crear el pago y recibir el webhook (requiere Firebase Blaze).
- Envío por zona y luego Envia.com o Skydropx para cotizar y generar guías.
- Panel de pedidos, confirmaciones, términos y política de devoluciones.

## 5. DNS de celinki.com (Namecheap)

Hoy: página de estacionamiento de Namecheap y reenvío de correo de Namecheap (registros MX `eforward*` y TXT SPF).

Cambios, en **Advanced DNS**:

| Tipo | Host | Valor |
|---|---|---|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| CNAME | www | alejandrogmota.github.io. |
| TXT | _github-pages-challenge-AlejandroGMota | (valor que dé GitHub) |

- Quitar los registros de estacionamiento (`URL Redirect` / `parkingpage`).
- No tocar el reenvío de correo (MX y SPF).
- Orden seguro: (1) verificar el dominio en GitHub con el TXT, (2) publicar el repo con `CNAME`, (3) cambiar A y CNAME, (4) activar «Enforce HTTPS» cuando GitHub emita el certificado.

## 6. Decisiones abiertas
- Marca: el sitio es **Celinki** y el local en Maps es **GAMMA**. El sitio menciona a GAMMA como punto de venta y de recolección.
- ¿Mismo proyecto de Firebase que Accesorios-compras, o uno aparte para separar el muestrario público de la operación interna?
- ¿Mostrar precios en el muestrario o solo «pregunta por WhatsApp»?
- ¿Quién da de alta los productos y las fotos?
