# Brief del build

Construye la landing descrita en [`LANDING-PROMPT.md`](LANDING-PROMPT.md).
Ese archivo manda; esto solo fija lo que el prompt no puede saber.

## Desviaciones del prompt

- El prompt dice `landing/index.html`. Aquí el repo **es** la landing:
  el archivo va en `index.html`, en la raíz. GitHub Pages sirve la raíz de `main`.
- Los assets van en `assets/`, no junto al HTML.

## Antes de escribir CSS

Carga las skills en el orden de §0: `frontend-design`, `ui-ux-pro-max`,
`impeccable`. `artifact-design` solo si además se publica como Artifact.

## Assets (§10)

- `assets/photo.jpg` — la foto original. **La pone Sergio**, no se genera.
- `assets/generated.jpg` y `assets/video.mp4` — se generan con el MCP de
  Higgsfield, ya configurado para esta carpeta. Comprueba con `/mcp` que
  aparece conectado antes de empezar.
- Si el MCP no responde: usa <https://ia-generator-openspec.vercel.app/> con la
  misma foto y descarga el resultado. Los tres assets tienen que ser la misma
  cadena foto → imagen → video, o la secuencia del héroe miente.
- Capturas de `/capture` y `/result` a 360px, más la imagen Open Graph 1200×630.

## Flujo de entrega

```bash
git checkout -b landing
# construir index.html + assets/
git add -A && git commit -m "Landing page"
git push -u origin landing
gh pr create --fill --base main
```

Tras el merge, activar Pages: **Settings → Pages → Source: Deploy from a
branch → `main` / root**. Sin workflow de Actions — el token de `gh` no tiene
scope `workflow`.

URL final: <https://sjunka.github.io/ai-gen-landing/>

## Terminado

El checklist mecánico de §12 del prompt, entero. Ninguna línea se opina.
