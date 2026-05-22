# Iterative Solvers for the Discrete Helmholtz Equation

This project implements a finite difference discretization of the complex Helmholtz equation and compares direct and iterative methods for solving the resulting sparse complex linear systems. The project focuses on convergence behavior, preconditioning, and computational performance. This project was developed as part of the Scientific Computing course at TU Delft.

## Problem

The complex Helmholtz equation is defined as

$$
-\frac{\partial^2 u}{\partial x^2} - \frac{\partial^2 u}{\partial y^2} - c(x,y)\hat{i}u = f(x,y), \quad (x,y)\in\Omega,
$$

$$
u = g(x,y), \quad (x,y)\in\partial\Omega,
$$

where $\Omega = (0,1)^2$. We choose $c(x,y)=2$, and $f(x,y)$ and $g(x,y)$ such that

$$
u_{ex}(x,y)=x(1-x)y^3(1-y)+e^x
$$

is the exact solution. The domain is discretized using a uniform finite difference grid with mesh size

$$
h=\frac{1}{N}.
$$

## Implemented Methods
- Direct sparse solver
- Gauss-Seidel
- COCG
- GMRES
- Preconditioned COCG using an Incomplete Cholesky (IC) preconditioner constructed from the real part of the system matrix
- Preconditioned GMRES using a complex IC preconditioner

## Results
The notebook contains:

- Convergence studies
- Residual reduction analysis
- Runtime comparisons
- Error analysis
- Convergence plots for multiple grid resolutions

The experiments investigate the effect of preconditioning on convergence speed and scalability.

## Running the Project

The project was developed and tested using Python 3.12. Install the required packages:
pip install -r requirements.txt

Open the notebook:

jupyter notebook notebooks/helmholtz_iterative_solvers.ipynb

The solver can be selected inside the notebook by modifying the solver variable in the experiment configuration section.
