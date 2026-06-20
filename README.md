# Snake 🐍

Clásico juego de la serpiente, jugable directamente desde el navegador. Hecho en **JavaScript + HTML5 Canvas**, sin dependencias ni build: un único archivo estático (~10 KB).

## ▶️ Jugar ahora

**[https://rodrigoulloa.github.io/Snake/](https://rodrigoulloa.github.io/Snake/)**

Sin instalar nada: abre la URL y juega, en desktop o en celular.

## 🎮 Cómo se juega

- Mueve la serpiente para comer la comida 🟠 y crecer.
- Cada comida suma **+1** al puntaje. La velocidad aumenta poco a poco.
- Pierdes si chocas contra una **pared** o contra **tu propio cuerpo**.
- Se guarda tu **récord** en el navegador (localStorage).

### Controles

| Acción | Desktop | Móvil |
|---|---|---|
| Mover | Flechas o `W` `A` `S` `D` | Deslizar el dedo (swipe) desde cualquier parte de la pantalla |
| Pausar / continuar | `Espacio` | Botón en pantalla |
| Reiniciar | Botón **Reintentar** | Botón **Reintentar** |

## 🏗️ Arquitectura

Todo vive en `docs/index.html`, organizado en capas claras y desacopladas:

- **Model** — estado del juego (grilla, serpiente, comida, dirección).
- **Actions** — lógica pura: funciones que reciben un estado y devuelven el siguiente (mover, comer, validar dirección, colisiones). Sin efectos sobre el DOM.
- **View + Loop** — render en `<canvas>` y el game loop con `requestAnimationFrame`.

Esta separación mantiene la lógica del juego testeable e independiente de cómo se dibuja.

## 🚀 Despliegue

Sitio 100% estático. Se publica con **GitHub Pages** desde la carpeta `/docs` de la rama `master`
(*Settings → Pages → Deploy from a branch → `master` / `/docs`*).
