# celinki.com — plan de SEO y de búsqueda con IA

Fecha: 2026-10-13. Objetivo: aparecer cuando alguien busque (en Google, Google Maps, ChatGPT, Gemini, Perplexity o Claude) cosas como «micas de hidrogel Pachuca», «mica de privacidad mayoreo Mineral de la Reforma», «proveedor de hidrogel Hidalgo», «cortadora KASR precio México».

## Cómo encuentran negocios locales los buscadores y las IA (resumen)
- **Google y Google Maps** se basan en el **Perfil de Negocio**, la relevancia del sitio, la distancia y las reseñas.
- **Las IA** (ChatGPT, Perplexity, Gemini, Claude) responden con lo que encuentran en la web: el sitio, el Perfil de Negocio, directorios y menciones. Para buscar en vivo usan sus propios rastreadores (OAI-SearchBot, PerplexityBot, Claude-SearchBot) y también índices de Google y Bing; si se bloquean en `robots.txt`, el sitio no sale en sus respuestas.
- Las IA citan mejor el texto **concreto y autocontenido**: un párrafo que diga qué vendes, dónde, a qué precio y cómo pedir, sin depender del resto de la página.
- `llms.txt` es una propuesta, no un estándar: Google dijo que no lo usa y ningún proveedor lo ha confirmado como señal. Se agrega porque no cuesta nada, sin esperar mucho de él.
- **Datos estructurados (JSON-LD)**: Google los recomienda; deben coincidir con lo que se ve en la página (precio como número, moneda `MXN`).
- **Consistencia de nombre, dirección y teléfono (NAP)** en todas partes: sitio, Google, Facebook, directorios.

## Ya hecho (2026-10-13)
- [x] `robots.txt` que permite Google, Bing y los rastreadores de búsqueda de ChatGPT, Perplexity y Claude, con enlace al sitemap.
- [x] `sitemap.xml`.
- [x] `llms.txt` con resumen del negocio, precios, zonas, cómo pedir y contacto.
- [x] JSON-LD `Store` (dirección, coordenadas, horario, teléfono, zonas atendidas: Pachuca y Mineral de la Reforma) con `OfferCatalog` generado de los mismos precios que se ven en la página.
- [x] Título con palabras de búsqueda: «Micas de hidrogel cortadas a tu modelo · Pachuca y Mineral de la Reforma | Celinki»; `lang="es-MX"`; Open Graph completo para que se vea bien al compartir por WhatsApp/Facebook.

## Pendientes (por prioridad)

### 1. Google (lo que más pesa para búsquedas locales)
- [ ] **Google Search Console**: verificar `celinki.com` (registro TXT en Namecheap) y enviar el sitemap. *Lo haces tú con tu cuenta de Google; yo puedo agregar el TXT en Namecheap.*
- [ ] **Perfil de Negocio GAMMA**: terminar la verificación con video; poner sitio web `https://celinki.com`, categoría secundaria «Proveedor de accesorios para teléfonos celulares» o similar, fotos reales, productos (cada tipo de mica) y publicaciones.
- [ ] **Decidir teléfono público**: el Perfil de Negocio tiene 771 103 0032 y el sitio 771 868 2542. Para Google conviene uno solo en todas partes (o poner el segundo como teléfono adicional en el perfil).
- [ ] **Reseñas**: pedir a los primeros vendedores que dejen reseña en Google mencionando «hidrogel», «Pachuca», «entrega».
- [ ] Bing Webmaster Tools (importa desde Search Console en minutos); alimenta a ChatGPT y Copilot.

### 2. Contenido en el sitio
- [ ] **Sección de preguntas frecuentes** con JSON-LD `FAQPage`: ¿qué es la mica de hidrogel?, ¿diferencia HD, mate y privacidad?, ¿cortan para mi modelo?, ¿cuánto tarda la entrega?, ¿mínimo para entrega gratis?, ¿cómo se paga?, ¿tienen para tablet?
- [ ] **Párrafo «Quiénes somos»** autocontenido: Celinki, proveedor de micas de hidrogel KASR en Pachuca y Mineral de la Reforma, desde cuándo, qué ofrece.
- [ ] **Páginas por tema** (cuando haya tiempo): `/privacidad`, `/tablet`, `/cortadoras`, `/entregas-pachuca`, cada una con su título, descripción y contenido propio. Más páginas útiles = más búsquedas cubiertas.
- [ ] `alt` descriptivo en todas las imágenes (hoy ya tienen; revisar que digan tipo + «mica de hidrogel»).
- [ ] Imagen para compartir de 1200×630 (`og:image`) con logo, «Micas de hidrogel» y «Entrega gratis Pachuca · Mineral de la Reforma».

### 3. Presencia fuera del sitio (lo que leen las IA)
- [ ] **Facebook**: página «Celinki · Micas de hidrogel» con el mismo nombre, dirección, teléfono y enlace; publicar en grupos de técnicos y vendedores de celulares de Pachuca.
- [ ] **Mercado Libre / Marketplace**: publicaciones que enlacen o mencionen celinki.com.
- [ ] Directorios locales mexicanos (Sección Amarilla, Cylex, Infobel) con datos idénticos.
- [ ] Menciones: que algún blog, grupo o tienda local hable de Celinki y enlace al sitio.

### 4. Técnico
- [ ] Imágenes WebP y prueba de velocidad (Lighthouse móvil ≥ 90); la velocidad cuenta para Google.
- [ ] Analítica (Google Analytics 4 o Plausible) para ver búsquedas, origen (QR del volante: `utm_source=volante`) y clics a WhatsApp.
- [ ] Validar datos estructurados en la herramienta «Prueba de resultados enriquecidos» de Google cada vez que cambien precios.
- [ ] Actualizar `lastmod` del sitemap y `llms.txt` cuando cambien precios o productos.

### 5. Revisar cada mes
- [ ] En Search Console: con qué búsquedas aparece y cuáles reciben clic.
- [ ] Preguntar a ChatGPT, Perplexity y Gemini «¿dónde compro micas de hidrogel a mayoreo en Pachuca?» y anotar si aparece Celinki.

## Fuentes consultadas
- Guías sobre aparecer en ChatGPT, Gemini y Perplexity: techwyse.com, pristren.com, webscraft.org (2026).
- Rastreadores de IA y robots.txt: help.otterly.ai, vydai.inweb.ua, growthmk.com.
- Datos estructurados LocalBusiness y comercio: documentación de Google Search Central y Merchant Center.

## Decisión 2026-10-13: dos negocios, dos perfiles
- **GAMMA Accesorios para celular** (tienda en Plaza Tere): Perfil de Negocio ya creado, teléfono 771 103 0032. Se queda para accesorios.
- **Celinki · Micas de hidrogel**: perfil nuevo y separado, teléfono **771 868 2542**, sitio `https://celinki.com`.
  - Tipo: **negocio de servicio a domicilio (área de servicio)**, sin dirección pública o con Plaza Tere solo como punto de recolección; zonas: Pachuca de Soto y Mineral de la Reforma.
  - Categoría sugerida: «Proveedor de accesorios para teléfonos celulares» / «Mayorista»; descripción centrada en hidrogel, corte a modelo y entrega gratis.
  - Mismo nombre, teléfono y sitio en Facebook, Mercado Libre y directorios.
- [x] Perfil «Celinki» creado en Google Business (2026-10-13): categoría Tienda de accesorios para teléfonos celulares, área de servicio Pachuca de Soto y Mineral de la Reforma, tel. 771 868 2542, sitio celinki.com, chat por WhatsApp. Dirección de verificación privada (no pública).
- [ ] Verificar el perfil con video desde el celular (Google Maps o business.google.com, cuenta cmke14y@gmail.com).
- [x] Horario: domingo a viernes 24 horas, sábado cerrado; descripción cargada (2026-10-13).
- [ ] Al verificarse: fotos reales, productos (cada tipo de mica) y categoría adicional «Mayorista».
- [ ] Decidir si usar el crédito de Google Ads de MXN 7,000 que ofreció Google (requiere cuenta de Ads con forma de pago).
- [ ] En el sitio, los datos estructurados ya son de Celinki (no de GAMMA) con el 771 868 2542.
