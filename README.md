# Nonlinear Heat Equation Simulation using FEniCSx and PyVista
## Author: Souvik Roy
This repository contains a simulation of a nonlinear heat conduction problem in a 3D domain using the finite element method (FEM). The simulation is solved using [DOLFINx](https://docs.fenicsproject.org/dolfinx/main/) and visualized using [PyVista](https://docs.pyvista.org/). The top surface of the domain receives a time-varying random temperature input, and the rest of the boundary is held at a fixed temperature. A nonlinear diffusion coefficient is used to model temperature-dependent conductivity.

## 🔧 Problem Description

- **Domain**: 3D cube \( [0, 1]^3 \)
- **Boundary Conditions**:
  - Top surface: Random temperature input between 30–100°C at every time step
  - Other surfaces: Fixed at 20°C
- **Initial Condition**: 20°C everywhere
- **Nonlinear Diffusion Coefficient**:
  \[
  k(u) = 1 + \frac{2}{1 + \exp(-10(u - 0.5))}
  \]
- **Time Stepping**:
  - Time step size: \( \Delta t = 0.00068587 \)
  - Total steps: 100

The simulation saves animated slices (XZ, XY, and Input surface) as a `.gif` file.

---

## 📦 Dependencies

To run this code, you'll need to install the following Python packages:

### Required Packages

- `dolfinx`
- `pyvista`
- `petsc4py`
- `mpi4py`
- `matplotlib`
- `numpy`

### Recommended Setup

It's highly recommended to use a `conda` environment or Docker container for compatibility with `dolfinx`.

### 1. Using Conda and pip (Linux/macOS):

```bash
# Create and activate a new environment
conda create -n fenicsx_env python=3.10 -y
conda activate fenicsx_env

# Install system dependencies (Ubuntu/Debian)
sudo apt-get install -y libopenmpi-dev

# Install petsc4py and mpi4py
pip install mpi4py petsc4py

# Install dolfinx
pip install --index-url https://wheels.fenicsproject.org/simple fenics-dolfinx

# Install visualization tools
pip install pyvista matplotlib

Author is not responsible for successful execution of the code.

