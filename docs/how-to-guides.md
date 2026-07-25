---
This part of the project documentation focuses on a **problem-oriented** approach.  
It provides practical, step-by-step guides to help you solve real-world tasks using **EStA**.
---

# How-To Guides

These guides walk you through common workflows — from installation to advanced analysis — with clear examples and code snippets.

### :material-download: Installation and Setup
**How to install EStA and set up your environment**

Learn how to get EStA up and running quickly.

- Install via **pip**, **conda**, or from source [TODO]
- Installing dependencies (`ase`, `spglib`, Fortran/C extensions, etc.)
- Verifying the installation with built-in tests and tutorials [on-going]

[:material-arrow-right-bold: Get Started →](https://sonuphysics.github.io/esta3/explanation){ .md-button .md-button--primary style="background-color:rgba(20, 182, 36, 0.68); color: white; font-weight: bold;" }

---

### :material-file-edit: Input File Generation
**How to automatically generate input files for calculations**

Create high-quality input files for leading electronic structure codes in seconds.

- Generate inputs for **VASP**, **Quantum ESPRESSO**, **Gaussian**, and more
- Configure k-points, pseudopotentials, convergence parameters, and advanced settings
- Use convenient functions like `esta.qeBag.gen_qeinput()` and `gen_qeinput2()`

[:material-arrow-right-bold: Learn More →](https://sonuphysics.github.io/esta3/tutorials/){ .md-button .md-button--primary style="background-color:rgb(20, 182, 36); color: white; font-weight: bold;" }

---

### :material-chart-bar: Output Analysis
**How to read and analyze results from electronic structure calculations**

Extract valuable insights from simulation outputs efficiently.

- Extract electronic band structures, k-points, and band gaps (`esta.qeBag.bands_kpts_band_gap`)
- Parse force constants and phonon data from the `phonon` subpackage
- Handle multiple output formats (XML, JSON, YAML, etc.)

---

### :material-lightbulb-on: Phonon & Thermodynamic Analysis
**How to perform vibrational and thermodynamic calculations**

- Compute phonon frequencies, densities of states, and thermodynamic properties
- Analyze zero-point energy, free energy, and heat capacity
- Extract and interpret force constants from Phonopy or internal calculations

---

### :material-map-search: Transition State Search
**How to find transition states and NEB paths**

- Set up and run **CI-NEB** calculations (interfaced with Quantum ESPRESSO)
- Optimize reaction pathways using `esta.transitionState.neb` and associated optimizers
- Visualize minimum energy paths

---

### :material-cube-scan: Structure Manipulation
**How to modify and transform atomic structures**

Powerful tools for crystal and molecular engineering:

- Atomic substitution, deletion, and duplication
- Cell transformations, vacuum layer addition, and supercell creation
- Lattice and coordinate manipulations via the `esta.general` module


* **Modelling Real-World Physics & Imperfections:** Idealized periodic bulk crystals are rare in nature. Manipulating structures allows researchers to model real-world complexities such as defects, grain boundaries, surfaces, and interfaces.
* **Exploring Potential Energy Surfaces (PES):** By systematically distorting cell parameters, straining lattices, or displacing atoms, computational scripts can map out energy landscapes, phase transition pathways, and reaction barriers.
* **Reducing Computational Cost:** Creating high-symmetry primitive cells or minimal representative supercells reduces the number of degrees of freedom, dramatically accelerating Density Functional Theory (DFT) calculations.
* **Bridge Between Experiments and Theory:** Manipulating crystal lattices allows direct matching of experimental conditions such as high pressure, epitaxial strain in thin films, or high temperature expansion.
* **Automated Data Generation for AI/ML:** Large-scale high-throughput screening relies on programmatic structure manipulation to generate thousands of diverse atomic configurations for training Machine Learning Interatomic Potentials (MLIPs).


### :material-application-cog: Key Applications & Use Cases

#### 1. Lattice & Supercell Transformations
* **Primitive to Conventional Conversions:** Converting primitive cells to conventional cells (and vice versa) for standardized physical analysis and visualization.
* **Supercell Generation:** Scaling unit cells ($N \times M \times K$) to model low-concentration dopants, alloy disorder, or long-wavelength acoustic phonons.
* **Lattice Strain & Stress Simulation:** Applying uniaxial, biaxial, or hydrostatic strain to evaluate elastic constants ($C_{ij}$), piezoelectric response, or strain-engineered bandgap tuning.

#### 2. Surface & Interface Modeling
* **Slab Generation & Vacuum Padding:** Cutting specific Miller indices $(hkl)$ to create surfaces and adding vacuum layers to isolate periodic images in 2D or surface calculations.
* **Heterostructure & Interface Building:** Matching lattice constants between disparate materials to model semiconductor heterojunctions, catalyst-support interfaces, or van der Waals stacks.
* **Adsorption Site Identification:** Generating symmetric binding positions on surface sites for molecule-catalyst interaction studies (e.g., ORR, HER, NR3).

#### 3. Defect & Disorder Engineering
* **Point Defects:** Creating vacancies, substitutional impurities, and interstitial atoms to compute formation energies and defect transition levels.
* **Extended Defects:** Building dislocations, stacking faults, and grain boundaries to evaluate mechanical degradation and thermal boundary resistance.
* **Special Quasirandom Structures (SQS):** Generating disordered solid-solution models that mimic random alloys without requiring infinite cell sizes.

#### 4. Lattice Dynamics & Thermal Transport
* **Finite-Displacement Phonon Calculations:** Displacing individual atoms along symmetry-inequivalent directions to calculate force constants, phonon dispersion relations, and thermal conductivity.
* **Thermal Expansion & Anharmonicity:** Modifying cell volumes to simulate Quasi-Harmonic Approximation (QHA) parameters for high-temperature thermodynamic properties.

#### 5. Molecular & Nanomaterial Systems
* **Conformational Sampling:** Rotating molecular dihedral angles and bonds to identify low-energy conformers.
* **Nanotube & Nanoribbon Construction:** Rolling up 2D sheets (e.g., graphene, MoS₂) into 1D nanotubes or cutting them into nanoribbons with specified edge terminations (zigzag/armchair).


---

## :material-matrix: Metric Tensor Calculations
**How to compute the metric tensor of a lattice**

EStA provides dedicated tools to calculate the **metric tensor** (`g`) and its inverse for any crystal lattice. This is essential for:

- Computing interatomic distances and angles accurately
- Transforming coordinates between Cartesian and fractional systems
- Analyzing lattice symmetry and strain

**Example usage:**

```py
from esta.general import metric_tensor

#Compute metric tensor from lattice vectors
g = metric_tensor(lattice_vectors)
print(g)
```