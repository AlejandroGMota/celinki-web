# celinki-web

Sitio de **Celinki** en [celinki.com](https://celinki.com): micas de hidrogel KASR a mayoreo para vendedores y técnicos de Pachuca y Mineral de la Reforma, cortadas al tamaño del modelo que elija el cliente o en lámina sin corte (mismo precio), con entrega gratis y pedidos por WhatsApp (771 868 2542). También muestra las cortadoras de hidrogel KASR.

Celinki (hidrogel) es un negocio distinto de **GAMMA Accesorios para celular** (tienda en Plaza Tere); GAMMA solo aparece como punto de recolección.

## Cómo está hecho
- **Astro**, una sola página: `src/pages/index.astro` (datos, marcado y estilos en el mismo archivo).
- **GitHub Pages** con `.github/workflows/deploy.yml`: cada push a `main` construye y publica (~1 minuto). Dominio en `public/CNAME`; DNS en Namecheap (`docs/PLAN.md`, sección 5).
- Nada se instala ni se construye en local; se prueba en el sitio publicado.

## Dónde se cambia qué
| Cambio | Dónde |
|---|---|
| Precios, tipos de mica, fotos | Arreglos `celular` y `tablet` en `src/pages/index.astro`. Repetir el cambio en `public/llms.txt`. Los datos estructurados (JSON-LD) se generan solos de esos arreglos |
| Cortadoras (precio = PDF de KASR + $2,500) | Arreglo `cortadoras` en `src/pages/index.astro` |
| Preguntas frecuentes | Arreglo `preguntas` (también alimenta el JSON-LD `FAQPage`) |
| Teléfono de WhatsApp | `telHidrogel` en `src/pages/index.astro` y `public/llms.txt` |
| Imágenes | `public/img/hidrogel/`, `public/img/cortadoras/`, `public/img/pasos/`, `public/img/iconos/`; imagen para compartir `public/img/compartir.jpg` (1200×630) |
| SEO | `public/robots.txt`, `public/sitemap.xml` (actualizar `lastmod`), `public/llms.txt`, metadatos en el `<head>` |

## Documentos (`docs/`)
| Archivo | Qué es |
|---|---|
| `PLAN.md` | Plan general, decisiones y DNS |
| `PLAN-visual.md` | Revisión crítica y diseño; volante |
| `PLAN-responsive.md` | Celular primero y WhatsApp primero |
| `PLAN-seo.md` | SEO, búsqueda con IA, perfiles de Google |
| `CHECKLIST-contenido.md` | Contenido y lo pendiente para producción |
| `catalogo-hidrogel.md` | Tipos, precios y hoja KASR de cada mica |
| `logo/` | Tres propuestas de logo (falta elegir) |
| `volante/` | Volante imprimible carta, 4 por hoja, con QR (`volante-carta-4.pdf`) |
| `referencias/` | Imágenes y videos de KASR (fuera del repo, `.gitignore`) |

Fuera del repo, por ser privados: costos y competencia en `../ventas/margenes-y-competencia-hidrogel.md`; paquetes para Marketplace en `../marketing-publicidad/paquetes-hidrogel-marketplace.md`; PDF de precios de KASR (ignorado).

## Cuentas y servicios
- GitHub Pages: repo `AlejandroGMota/celinki-web`, dominio verificado.
- Google Search Console: propiedad de dominio `celinki.com` verificada, sitemap enviado (2026-10-13).
- Perfil de Negocio de Google «Celinki»: creado, falta verificar con video (cuenta cmke14y@gmail.com).
