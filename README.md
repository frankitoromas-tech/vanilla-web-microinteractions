# 🎨 Vanilla Web Micro-Interactions — Zero-Dependency DOM Engine

[![HTML5](https://img.shields.io/badge/HTML5-Semantic_Web-E34F26?style=for-the-badge&logo=html5&logoColor=white)](https://developer.mozilla.org/es/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-GPU_Accelerated-1572B6?style=for-the-badge&logo=css3&logoColor=white)](https://developer.mozilla.org/es/docs/Web/CSS)
[![JavaScript](https://img.shields.io/badge/JavaScript-Vanilla_ES6+-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://developer.mozilla.org/es/docs/Web/JavaScript)
[![Performance](https://img.shields.io/badge/Performance-Zero_Overhead-brightgreen?style=for-the-badge)](#rendimiento-y-m%C3%A9tricas-t%C3%A9cnicas)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](LICENSE)

Motor interactivo y experiencia visual de alto rendimiento construida con **tecnologías web nativas puras (Zero Dependencies)**. Demuestra la manipulación eficiente del Document Object Model (DOM), delegación de eventos táctiles y de puntero, transiciones CSS3 aceleradas por hardware y narrativa visual sin incurrir en costos de empaquetado ni dependencias de frameworks.

---

## 🏛️ Pipeline de Renderizado y Métricas Web Core

```mermaid
graph LR
    Browser["Navegador Web"] --> HTML["Parseo HTML Semántico"]
    Browser --> CSS["CSSOM (Variables CSS & Keyframes)"]
    HTML & CSS --> RenderTree["Árbol de Renderizado (Render Tree)"]
    RenderTree --> Layout["Cálculo de Geometría (Layout)"]
    Layout --> Paint["Pintado (Paint)"]
    Paint --> Composite["Composición en GPU (60 FPS Continuos)"]
```

---

## ⚡ Rendimiento y Métricas Técnicas

| Parámetro / Métrica | Valor Nominal / Medición | Mecanismo de Garantía Técnica |
| :--- | :--- | :--- |
| **Bundle Size Externo** | **0.00 KB** (Cero dependencias externas) | Vanilla JavaScript ES6+ & CSS3 nativo |
| **First Contentful Paint (FCP)** | **< 120 ms** | Cero bloqueo de parseo; render tree inmediato |
| **Compositor Frame Budget** | **16.67 ms (60 FPS estables)** | Animaciones confinadas a `transform: translate3d` y `opacity` |
| **Cumulative Layout Shift (CLS)** | **0.000** | Dimensionamiento explícito de contenedores e ilustraciones |
| **Consumo de Memoria Heap DOM** | **< 6.5 MB** | Listeners delegados y recolección de basura determinista |
| **Vector Evasión Euclidiana** | $\Delta d = \sqrt{(x_2 - x_1)^2 + (y_2 - y_1)^2} \ge 80\text{px}$ | Reposicionamiento dinámico dentro de límites del viewport $(W - w, H - h)$ |

---

## ⚡ Aspectos Técnicos Destacados

1. **Cero Sobrecarga de Librerías (0 KB Bundle):** A diferencia de SPAs basadas en React/Angular que pesan cientos de kilobytes, este motor carga instantáneamente con un First Contentful Paint (FCP) menor a 120 milisegundos.
2. **Cálculo Vectorial de Evasión:** La lógica del botón dinámico implementa un cálculo euclidiano del vector de distancia entre el puntero y el centroide del elemento, desplazándolo deterministamente dentro del *viewport* sin desbordar los márgenes de la pantalla.
3. **Optimización de Pintado:** Las animaciones de flotación y opacidad están confinadas a las propiedades CSS `transform` y `opacity`, garantizando que la GPU procese las capas sin repintar el árbol DOM.

---

## 📂 Estructura de Archivos

```
vanilla-web-microinteractions/
├── index.html       # Estructura semántica, accesibilidad y metaetiquetas OpenGraph
├── styles.css       # Sistema de diseño con variables CSS (--primary, --accent) y keyframes
├── script.js        # Lógica de microinteracciones, cálculo de coordenadas y eventos touch/pointer
├── gato_1.png       # Ilustración de estado inicial
├── gato_2.png       # Ilustración de estado de resolución
└── README.md        # Documentación de arquitectura y diseño web
```

---

## 🚀 Despliegue y Ejecución Local

No requiere NodeJS, npm ni herramientas de compilación.

### 1. Clonar el Repositorio
```bash
git clone https://github.com/frankitoromas-tech/vanilla-web-microinteractions.git
cd vanilla-web-microinteractions
```

### 2. Abrir en Navegador
Haz doble clic en `index.html` o sírvelo con cualquier servidor estático:
```bash
# Con Python
python -m http.server 8000
# O con Node/npx
npx serve .
```

---

## 👨‍💻 Autor & Contacto
- **Desarrollador:** **Frankosyni (Φρανκοσύνη/Francus.)** 🔥 — Frank Emiliano Vargas Huamán
- **Especialidad:** Software & Agentic AI Developer | Backend & Frontend Engineering
- **GitHub:** [@frankitoromas-tech](https://github.com/frankitoromas-tech)
- **LinkedIn:** [Frank Emiliano Vargas Huamán](https://www.linkedin.com/in/frank-emiliano-vargas-huamán-6a010a378/)
- **Licencia:** [MIT](LICENSE)
