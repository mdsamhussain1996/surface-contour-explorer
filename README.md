# Surface & Contour Explorer 🏔️

An interactive, single-page pedagogical web application designed for undergraduate multivariable calculus students and educators to visualize functions of two variables $z = f(x, y)$, their 3D surfaces, and matching 2D contour maps.

## 🌟 Highlights

- **Dual Mode Visualization:**
  - **📊 Explorer Mode:** Side-by-side synchronized 3D surface and 2D contour plot with a real-time cutting plane at $z = c$, projected level curves, and an optional 3D full-stack sliced view.
  - **🏗️ Build the Surface Step by Step Mode:** A progressive pedagogical walkthrough that deconstructs the 3D surface:
    1. **Put $y = 0$:** Slice with the $xz$-plane to discover the wall curve $z = f(x, 0)$
    2. **Put $x = 0$:** Slice with the $yz$-plane to discover the wall curve $z = f(0, y)$ and test directional symmetry
    3. **Build the Surface:** Automatically detects radial symmetry ($r = \sqrt{x^2 + y^2}$) to rotate the profile curve about the $z$-axis in 3D, or sweeps planar slices along $x$ or $y$ to paint the surface
    4. **The Full Surface:** Slices with horizontal planes $z = c$ to generate level curves and drop them down to the coordinate floor
- **Safe Math Parsing:** Powered by [math.js](https://mathjs.org/) (`math.compile` and AST `node.transform`), supporting implicit multiplication (e.g. `3xy`), standard transcendental functions (`sqrt`, `exp`, `log`, `sin`, `cos`, `tan`, `abs`), and constants (`pi`, `e`). No `eval()` or `new Function()`.
- **Smooth 60 FPS Plotting:** Built with [Plotly.js](https://plotly.com/javascript/) WebGL surfaces, `Plotly.react`, and `requestAnimationFrame`, maintaining user camera angles across slider interactions and animations via `uirevision`.
- **Robust Singularity Handling:** Evaluates on a $91 \times 91$ grid (8,281 points). Automatically replaces non-real complex numbers (e.g. $\sqrt{1 - x^2 - y^2}$ outside the unit circle) and asymptotic poles with `null`, and applies 95th-percentile singularity clipping.
- **14 Built-In Classic Examples:**
  - Bowl ($x^2 + y^2$)
  - Elliptic bowl ($x^2 + 4y^2$)
  - Saddle hyperbolas ($x^2 - y^2$)
  - Saddle $z = xy$
  - Plane ($2x + y$)
  - Cone ($\sqrt{x^2 + y^2}$)
  - Parabolic contours ($y - x^2$)
  - Gaussian hill ($\exp(-(x^2 + y^2))$)
  - Two hills ($\exp(-((x-1)^2+y^2)) + \exp(-((x+1)^2+y^2))$)
  - Egg crate ($\sin(x)\cos(y)$)
  - Ripples ($\sin(\sqrt{x^2 + y^2})$)
  - Peaks & pits ($(x^2 + 3y^2)\exp(-x^2 - y^2)$)
  - Diamond ($|x| + |y|$)
  - Monkey saddle ($x^3 - 3xy^2$)
- **Classroom Tools:**
  - 🖥️ Presentation Mode with enlarged fonts and tall plots for projectors
  - 🔗 URL Hash Sharing preserving exact function, domain, and level $c$
  - 📷 High-resolution PNG export for student handouts and slides
  - ⌨️ Keyboard arrow shortcuts (Left/Right) for stepping through the build process

## 🚀 Live Demo

Launch the live web application on GitHub Pages:
[https://mdsamhussain1996.github.io/surface-contour-explorer/](https://mdsamhussain1996.github.io/surface-contour-explorer/)

## 💻 Tech Stack

- **HTML5, CSS3, ES6+ JavaScript:** 100% self-contained in a single `index.html` file with zero build tools or dependencies.
- **Plotly.js (v2.35.2):** WebGL 3D surfaces and 2D contour rendering.
- **math.js (v11.11.0):** Safe algebraic parsing, AST manipulation, and symbolic simplification.

## 📄 License

MIT License. Feel free to use and adapt in mathematics and engineering courses!
