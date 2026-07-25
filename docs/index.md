**EStA: Electronic Structure Automator**

<!-- *![EStA](./image/logo.jpg)  -->

<!-- ![The EStA logo](img/esta_logo2.6.0_cropped.png){: style="width:350px; height:200px;" } -->
![The EStA logo](img/esta_logo2.6.0_cropped.png){: style="display: block; margin: 0 auto; width: 450px; height:250px;"}

**Electronic Structure Automator** (EStA) is a Python-based software package (with components in modern Fortran and C) designed for analyzing, pre-processing, and post-processing data from various electronic structure calculation codes. It supports packages such as **VASP**, **Quantum ESPRESSO**, **Gaussian**, **xTB**, **ORCA**, and others.

EStA automates input file generation for multiple codes, performs model calculations, and provides tools for materials and molecular property analysis. Future plans include expanded capabilities for predicting electronic and transport properties.

---

## Features

- **Automatic input generation** for VASP, Quantum ESPRESSO, Gaussian, GRRM, and other electronic structure codes
- **Output analysis** supporting various formats (XML, YAML, JSON, etc.)
- **Vibrational and thermodynamic analysis** of atomic and molecular systems
- **Transition state search** using the CI-NEB method (currently interfaced with Quantum ESPRESSO)
- **Zone-center phonon calculations** (based on gradient input; planned expansion to the full Brillouin zone)
- **Model calculations** for lattice thermal conductivity (first-principles implementation is experimental)
- **Tight-binding calculations** for bulk materials
- **Point group detection** (space group and symmetry analysis powered by spglib)
- **Lattice transformation analysis**
- **Machine learning** predictions of key physical properties (more models coming soon)
- **Unit conversion utilities** — seamless handling of atomic units, SI units, and file formats like AXSF, BXSF, and CUBE for visualization
- **Force constant analysis** from Phonopy calculations (Γ-point or arbitrary q-points), including pair-wise interactions, distances, stretching, and bending constants
- **Infrared and Raman intensity calculations** for periodic systems (auto-generates files for computing the high-frequency dielectric constant ε∞)
- **Structure manipulation** — atomic substitution, deletion, extension, modulation, inversion, and more
- Additional routines (xTB-GRRM interfacing, minimization procedures, Fortran modules for static dielectric constant and mode oscillator strengths, etc.) are available and will be integrated into the main package soon

---

<div class="grid cards" markdown>

-   :material-clock-fast:{ .lg .middle } **Set up EStA**

    ---

    Install EStA and get up and running in minutes.

    [:octicons-arrow-right-24: Getting Started](explanation.md)

-   :material-material-design:{ .lg .middle } **Xlat and Xat Classes**

    ---

    Core classes for handling crystal lattices (`Xlat`) and atoms/molecules (`Xat`).

    [:octicons-arrow-right-24: Usage](tutorials.md)

-   :writing_hand:{ .lg .middle } **Measure Module: Units Handling**

    ---

    Comprehensive and easy-to-use unit conversion routines (atomic ↔ SI units and more).

    [:octicons-arrow-right-24: Documentation](tutorials.md)

-   :material-scale-balance:{ .lg .middle } **General & Quantum ESPRESSO Modules**

    ---

    Structure manipulation via the `General` module + convenient input generation for Quantum ESPRESSO.

    [:octicons-arrow-right-24: Usage](tutorials.md)

</div>

## Documentation Structure

The documentation is organized into four main sections:

1. **[Explanation](explanation.md)** — High-level overview and background
2. **[How-To Guides](how-to-guides.md)** — Practical step-by-step instructions
3. **[Tutorials](tutorials.md)** — Hands-on examples and walkthroughs
4. **[Reference](reference.md)** — API documentation and detailed module references

---

## Acknowledgements

Thank you to everyone who has supported, discussed, and contributed to the project throughout its development. Special thanks to **Dr. Savita Saini** for her continuous motivation, guidance at every stage, and incredible family support during weekends and intensive development periods.

---

*EStA is under active development. Contributions, bug reports, and feature requests are welcome.*
