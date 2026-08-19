# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Users

Gente evaluando el método, no el producto. Llegan desde la presentación o desde
el repositorio de la app y quieren dos cosas: ver que la app existe y funciona,
y entender cómo cuatro personas construyeron 80 archivos sin escribir el código
a mano.

El producto que la landing vende — la app — vive en otro repositorio:
<https://github.com/sjunka/speckit-ai-generator>. Aquí no hay código de
aplicación, solo la página.

## Product Purpose

Una foto entra, la IA la convierte en imagen, y esa imagen se vuelve un video
corto que se puede descargar o compartir. El producto terminado es la prueba;
el argumento real es el método con el que se construyó.

## Positioning

El código de la aplicación no se escribió a mano: está descrito en
`specs/001-ai-media-generator/spec.md`, repartido en 39 tickets y 5 fases, y el
agente lo construye ticket por ticket. Cada fase declara de qué archivos es
dueña y cuáles no toca, así que tres ramas corren en paralelo sin que dos
personas editen el mismo archivo. Eso es lo que un producto vecino no puede
copiar sin copiar la especificación entera.

## Operating Context

- El flujo de trabajo es GitHub Spec Kit: `/speckit-specify` → `/speckit-plan`
  → `/speckit-tasks` → `/speckit-implement`.
- Cuatro personas (Sergio, Mateo, Johan, Tomás) trabajan en ramas por fase:
  `main`, `001-frontend`, `001-backend`, `001-dashboard`.
- La fase 1 (T001–T009, la base y el sistema de diseño) está construida y
  fusionada en el `main` del repo de la app. Faltan las fases 2, 3, 4 y 5.
- El uso real de la app es de pie, con una mano, en un celular.

## Capabilities and Constraints

- La landing es HTML estático de un solo archivo con sus assets: sin build, sin
  framework, sin dependencias. `index.html` en la raíz, assets en `assets/`.
- Se publica con GitHub Pages desde `main` / root, sin workflow de Actions: el
  token de `gh` no tiene scope `workflow`. URL:
  <https://sjunka.github.io/ai-gen-landing/>.
- El contrato de la página es `LANDING-PROMPT.md`; `BUILD.md` fija lo que el
  prompt no puede saber (rutas, assets, flujo de entrega).
- Lo que la landing afirma del producto sale de la app: 39 tickets, 5 fases,
  Next.js 16, Clerk, MongoDB Atlas, Vercel Blob y Higgsfield.

## Brand Commitments

- Nombre: **AI Media Generator**. La voz es directa y sin marketing: frases
  cortas, cifras del repositorio en vez de cifras inventadas, y los tres
  estados reales del producto (foto, imagen, video) como argumento visual.
- Mundo visual comprometido (decisión del 2026-08-18): editorial claro, tomado
  de `docs/`/DESIGN-elevenlabs como referencia de color. Lienzo off-white
  `#f5f5f5`, tinta cálida casi negra `#0c0a09`, display en serif a peso 300, y
  orbes de gradiente pastel (mint, peach, lavender, sky, rose) como único
  momento de color. La píldora de tinta es la única acción con color; no hay
  color de marca saturado.
- Los tokens viven en el bloque `<style>` de `index.html`. La app tiene su
  propio sistema, oscuro, fijado en sus specs: **las dos superficies no
  comparten tokens** y no deben sincronizarse a la fuerza.

## Evidence on Hand

- `assets/photo.jpg` y `assets/generated.jpg`: el par antes/después real del
  héroe. La imagen generada salió de Higgsfield (`soul_2`) usando la foto como
  referencia el 2026-08-18.
- `assets/video.mp4`, `shot-capture.jpg`, `shot-result.jpg`, `shot-video.jpg` y
  `og.jpg` son **archivos de relleno**, no capturas reales.
  Hay que reemplazarlos con material del producto antes de presentar; nada de
  lo que se diga de ellos puede presentarse como una captura real.
- Los números de la landing (39 tickets, 5 fases, 4 personas, 80 archivos de
  código, 0 escritos a mano) salen del repositorio.
- No hay testimonios, clientes, precios ni benchmarks. No inventar ninguno.

## Product Principles

1. La página muestra los tres estados reales del producto — foto, imagen,
   video — antes de explicar nada.
2. Los números que se muestran son del repositorio de la app, no de marketing.
3. Ninguna afirmación sobre el producto se inventa aquí: si no está en los
   specs de la app, no va en la página.
4. Sin build ni dependencias. Un archivo, sus assets, y Pages.

## Accessibility & Inclusion

Se lee en celular tanto como en escritorio: objetivos táctiles de 44px como
mínimo, foco de teclado visible, `prefers-reduced-motion` respetado como última
regla de la hoja de estilos, y contraste de texto de cuerpo por encima de 4.5:1
sobre el lienzo claro.
