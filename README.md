# Snake 🐍

Clásico juego de la serpiente. Empezó como un proyecto en **Ruby + Ruby2D** (con lógica desacoplada y tests) y ahora cuenta con un **port web en JavaScript + HTML5 Canvas**, jugable directamente desde el navegador.

## ▶️ Jugar ahora

**[https://rodrigoulloa.github.io/Snake/](https://rodrigoulloa.github.io/Snake/)**

Sin instalar nada: abre la URL y juega.

## 🎮 Cómo se juega

- Mueve la serpiente para comer la comida 🟠 y crecer.
- Cada comida suma **+1** al puntaje. La velocidad aumenta poco a poco.
- Pierdes si chocas contra una **pared** o contra **tu propio cuerpo**.
- Se guarda tu **récord** en el navegador (localStorage).

### Controles

| Acción | Teclado | Móvil |
|---|---|---|
| Mover | Flechas o `W` `A` `S` `D` | Deslizar el dedo (swipe) |
| Pausar / continuar | `Espacio` | Botón en pantalla |
| Reiniciar | Botón **Reintentar** | Botón **Reintentar** |

## 🗂️ Estructura del proyecto

```
docs/index.html   → Versión web (JS/Canvas). Lo que sirve GitHub Pages.
src/              → Versión original en Ruby (escritorio, Ruby2D)
  model/          → Estado del juego
  actions/        → Lógica pura del juego
  view/           → Render con Ruby2D
test/             → Tests (Minitest) de la lógica
```

El port web conserva la misma separación en capas **Model / Actions (puras) / View**.

## 💻 Versión Ruby (escritorio)

Requiere Ruby y las gemas del `Gemfile`:

```bash
bundle install
ruby src/app.rb     # ejecuta el juego en una ventana de escritorio
ruby -Itest test/actions_test.rb   # corre los tests
```

> Nota: la versión Ruby usa Ruby2D (gráficos nativos de escritorio) y no corre en el navegador; para jugar en la web se usa el port de `docs/`.

## 🚀 Despliegue

La versión web es estática (un único archivo HTML, ~10 KB, sin dependencias). Se publica con **GitHub Pages** desde la carpeta `/docs` de la rama `master`.
