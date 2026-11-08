[README_Solow_GitHub_Fixed.md](https://github.com/user-attachments/files/34557360/README_Solow_GitHub_Fixed.md)
# Solow Growth Model: Capital Accumulation and Technological Progress

**Author:** Anaeli Pinto  
**Area:** Macroeconomic Theory · Economic Growth · Computational Economics  
**Tools:** Python, Jupyter Notebook, SymPy, NumPy, Matplotlib, ipywidgets

## Overview

This independent academic project implements the basic and extended Solow growth models using symbolic computation, numerical simulations, and interactive visualizations. Drawing on the Solow framework discussed in Gregory Mankiw's *Macroeconomics*, it explores capital accumulation, convergence to steady state, population growth, and labor-augmenting technological progress.

**Research objective:** Examine how changes in saving, depreciation, population growth, and technological progress affect steady-state capital and the dynamics of long-run growth.

## Theoretical Framework

*Equations are written in plain-text mathematical notation for consistent display on GitHub. `^` denotes exponentiation.*

### 1. Basic Solow Growth Model

The Cobb–Douglas production function is:

> **Yₜ = Kₜ^α · Lₜ^(1−α)**

Output per worker is:

> **yₜ = kₜ^α**

The discrete-time law of motion for capital per worker is:

> **kₜ₊₁ = s · kₜ^α + (1−δ) · kₜ**

At the steady state, investment offsets depreciation:

> **s · (k*)^α = δ · k***

Therefore:

> **k* = (s / δ)^[1 / (1−α)]**

### 2. Extended Model: Population Growth and Technology

With labor-augmenting technology, production is:

> **Yₜ = Kₜ^α · (AₜLₜ)^(1−α)**

Capital per effective worker is:

> **k̃ₜ = Kₜ / (AₜLₜ)**

The notebook implements the discrete-time transition equation:

> **k̃ₜ₊₁ = [s · k̃ₜ^α + (1−δ) · k̃ₜ] / [(1+n)(1+g)]**

For graphical comparisons, it also uses the conventional approximation:

> **s · (k̃*)^α = (δ+n+g) · k̃***

Which gives the approximate steady state:

> **k̃* = [s / (δ+n+g)]^[1 / (1−α)]**

**Technical note:** The approximate break-even expression used in some graphs is not identical to the exact discrete-time steady-state condition implied by the transition equation. The notebook explores both formulations.

## Computational Approach

- **Symbolic mathematics:** Represent production functions and solve steady-state expressions with SymPy.
- **Numerical simulation:** Compute capital accumulation paths from selected initial conditions using NumPy.
- **Comparative statics:** Change saving, depreciation, population growth, and technological progress parameters and examine shifts in steady states.
- **Visualization:** Plot investment, break-even investment, and convergence with Matplotlib.
- **Interactive exploration:** Use ipywidgets sliders to vary model parameters.

## Illustrative Parameters and Results

The basic-model numerical example uses:

| Parameter | Value |
| --- | ---: |
| Saving rate (`s`) | 0.25 |
| Depreciation rate (`delta`) | 0.05 |
| Capital share (`alpha`) | 0.30 |

The corresponding basic-model steady-state values are approximately **9.9662 for capital per worker** and **1.9932 for output per worker**.

The extended-model example additionally sets **population growth (`n`) to 0.02** and **technological progress (`g`) to 0.03**. These are illustrative model inputs, not estimates from observed data.

## Key Insights

- Greater saving raises steady-state capital per worker in the basic model.
- Higher depreciation lowers steady-state capital.
- Capital paths converge toward a steady state under the model assumptions.
- Population growth and technological progress change the break-even investment requirements for capital per effective worker.
- Sustained growth in output per worker in the extended model is linked to technological progress, not capital accumulation alone.

## Repository Files

- `solow_growth_model.ipynb` — notebook containing theoretical discussion, code, numerical simulations, graphs, and interactive controls.
- `README.md` — project overview, model equations, methods, and findings.

## How to Run

1. Download or clone this repository.
2. Install dependencies:

   ```bash
   pip install numpy sympy matplotlib ipywidgets notebook
   ```

3. Open `solow_growth_model.ipynb` in Jupyter Notebook or JupyterLab.
4. Run the cells in order and explore the interactive controls.

No external dataset is needed.

## Scope and Limitations

This is a **theoretical and computational economics project**, not an empirical econometric study. Its conclusions follow from the assumed production function, selected parameters, and simulation structure. The notebook also contains a section titled **“Different values for n”** with Python written in a Markdown cell; convert that cell to a code cell if you want its population-growth graph to execute.

## Conclusion

The project uses Python-based symbolic and numerical methods to examine how the Solow model connects saving, depreciation, demographic growth, and technological progress to steady-state outcomes and economic convergence.
