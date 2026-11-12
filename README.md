# Gargantua

![Gargantua Logo](https://raw.githubusercontent.com/kaizen-flims/Podium-Air/main/Logo.png)

A real-time, interactive black-hole visualization built with **Three.js** and custom GLSL shaders. The scene renders a gravitationally lensed star field and a glowing accretion disk around a Schwarzschild black hole, with cinematic post-processing.

## Live demo

Once GitHub Pages is enabled and the deployment workflow has completed, the site will be available at:

`https://kaizen-flims.github.io/Blackhole/`

## Features

- **Gravitational lensing:** A fragment shader traces light paths around the black hole using a Schwarzschild-inspired photon acceleration model.
- **Accretion disk:** Procedural noise, animated disk structure, Doppler beaming, and gravitational redshift create a dynamic, temperature-coloured disk.
- **Star field:** Procedurally generated stars and a subtle galactic band appear in the background.
- **Cinematic rendering:** Unreal Bloom, ACES filmic tone mapping, chromatic aberration, anamorphic streaks, and film grain.
- **Interactive camera:** Orbit the scene by dragging and zoom with the scroll wheel. The camera gently auto-rotates when idle.
- **Responsive canvas:** The renderer adjusts to the browser window size.

## Controls

| Input | Action |
| --- | --- |
| Drag | Orbit the camera |
| Scroll | Zoom in or out |
| Leave idle | Resume automatic camera rotation |

## Run locally

This is a static, single-page project. No build step or package installation is required.

1. Clone the repository:
   ```bash
   git clone https://github.com/kaizen-flims/Blackhole.git
   cd Blackhole
   ```
2. Serve the folder with any local HTTP server. For example, with Python:
   ```bash
   python -m http.server 8000
   ```
3. Open [http://localhost:8000](http://localhost:8000).

Opening the HTML file directly may work in some browsers, but using a local server is recommended for ES modules and import maps.

## Technology

- HTML and CSS
- JavaScript ES modules
- [Three.js 0.160.0](https://threejs.org/)
- GLSL vertex and fragment shaders
- Three.js OrbitControls and post-processing passes

Three.js is loaded from a public CDN (unpkg, with jsDelivr as a fallback), so an internet connection is required when loading the experience.

## Deployment

The repository includes a GitHub Actions workflow at `.github/workflows/deploy.yml`. Every push to `main` publishes the static site to GitHub Pages; it can also be started manually from the **Actions** tab.

### One-time GitHub Pages setup

1. Open **Settings → Pages** in this repository.
2. Under **Build and deployment → Source**, select **GitHub Actions**.
3. Ensure Actions are permitted to read repository contents and write Pages deployments (the workflow declares the required permissions).
4. Push to `main` or run **Deploy to GitHub Pages** manually from the Actions tab.

The deployment URL is `https://kaizen-flims.github.io/Blackhole/`.

## Project structure

```text
.
├── index.html
├── README.md
└── .github/
    └── workflows/
        └── deploy.yml
```

## Notes

- A modern browser with WebGL support is required.
- Rendering quality and performance depend on the device's GPU and browser.
- The visual simulation is an artistic, real-time approximation inspired by black-hole lensing, not a scientific instrument or a complete numerical relativity solver.
