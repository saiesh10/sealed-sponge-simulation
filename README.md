# Sealed Sponge Particle Scattering Simulation
> **Asian Paints Alchemy — Case 1: Whiteness Without TiO₂**  
> *An interactive, physics-based Monte Carlo radiative transport simulation illustrating why sealed low-refractive-index sponge particles retain whiteness in paint while open ones turn transparent.*

---

## 🔬 Scientific Context & Problem Overview
In architectural and industrial coatings, titanium dioxide ($\text{TiO}_2$) is the predominant white pigment due to its exceptionally high refractive index ($n \approx 2.7$). However, environmental impact and supply chain constraints motivate non-mineral, structural alternatives.

One promising alternative is **polymer void scattering** (e.g., disordered porous poly(methyl methacrylate) / PMMA matrices with air-filled submicron voids). 

- **The Wetting Problem (Scenario B):** When porous particles or films are incorporated into paint, the liquid resin binder ($n \approx 1.48–1.50$) spontaneously penetrates the pore network via capillary pressure:
  $$\Delta P = \frac{2\gamma \cos\theta}{r_{\text{pore}}}$$
  Because $n_{\text{binder}} \approx n_{\text{PMMA}} \approx 1.49$, the refractive index contrast vanishes ($\Delta n \to 0$). The transport mean free path $\ell_t$ diverges from $\sim 1\ \mu\text{m}$ to $>100\ \mu\text{m}$, and the film becomes translucent/transparent, exposing the dark backing.
- **The Sealed Sponge Hypothesis (Scenario C):** Encapsulating each porous particle within an impermeable, pinhole-free nano-skin barrier (~20–50 nm) prevents binder ingress. The core voids permanently retain dry air ($n = 1.00$), maintaining high optical contrast ($\Delta n = 0.49$) and sustaining diffuse white reflectance in wet and cured paint.

---

## ⚡ Key Features of this Interactive Simulation
- **Single Self-Contained Offline File:** Pure HTML5, Canvas, and SVG. Zero external libraries, CDNs, or build tools. Works 100% offline.
- **Monte Carlo Photon Transport Engine:** 3D isotropic random walk through a slab of thickness $L$ over an absorbing black substrate ($z = L$). Processes $20{,}000$ to $100{,}000$ photons asynchronously in a background Web Worker.
- **Three Comparative Scenarios:**
  - **Scenario A (Dry Open Film):** $\ell_t = 1.0\ \mu\text{m}$ (Literature benchmark: Syurik et al., *Adv. Funct. Mater.* 28, 1706901, 2018; reported $\sim 75\%$ reflectance at $4.0\ \mu\text{m}$).
  - **Scenario B (Wet / Flooded Film):** Flooded $\ell_t$ slider labeled `ASSUMPTION` (default $100\ \mu\text{m}$, range $10–500\ \mu\text{m}$) demonstrating loss of scattering.
  - **Scenario C (Sealed Sponge Particle):** Labeled `HYPOTHESIS, to be tested` ($\ell_t = 1.0\ \mu\text{m}$ preserved inside wet paint).
- **Live Trajectory Animation:** Animates 50 representative sample photon paths in real-time at 60 FPS.
- **Reflectance vs. Thickness Curve:** Interactive chart from $L = 1\ \mu\text{m}$ to $30\ \mu\text{m}$ with hover tooltips and literature reference marker.
- **Microstructural Cross-Section Schematics:** Clear vector SVG diagrams contrasting air voids, flooded resin, and core-shell impermeable skins.
- **CSV Data Export:** One-click download of the complete simulation sweep data.

---

## 🚀 How to Run Locally
Simply open `index.html` in any modern web browser (Google Chrome, Microsoft Edge, Mozilla Firefox, Safari).

---

## 🌐 How to Enable GitHub Pages (Live Demo)
1. In your GitHub repository, go to **Settings** → **Pages**.
2. Under **Build and deployment** → **Source**, select `Deploy from a branch`.
3. Choose the `main` branch and root `/` folder, then click **Save**.
4. Your simulation will be live at:
   `https://saiesh10.github.io/<repository-name>/`

---

## 📜 Scientific Honesty & Model Limitations
- **Permanent Top Banner:** Indicates illustrative simulation generated with AI assistance.
- **Limitations Modeled:**
  1. Isotropic scattering approximation ($g = 0$) using transport mean free path $\ell_t$.
  2. Zero optical absorption ($\mu_a = 0$).
  3. Omission of interface Fresnel reflection (explaining the honest discrepancy between simulated $\sim 69\%$ and Syurik et al.'s reported $\sim 75\%$).
  4. Scalar photons (polarization neglected).
  5. Geometric radiative transfer regime (thin-film interference omitted).
  6. Independent single scattering approximation.
