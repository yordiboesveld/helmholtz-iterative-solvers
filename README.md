# Iterative Solvers for the Discrete Helmholtz Equation

This project implements a finite difference discretization of the complex Helmholtz equation and compares direct and iterative methods for solving the resulting sparse complex linear systems. The project focuses on convergence behavior, preconditioning, and computational performance. This project was developed as part of the Scientific Computing course at TU Delft.

## Problem

The complex Helmholtz equation is defined as
$$
-\frac{\partial^2 u}{\partial x^2}
-\frac{\partial^2 u}{\partial y^2}
-c(x,y)\hat{i}u
=
f(x,y), \quad (x,y)\in\Omega
$$

where $\Omega = (0,1)^2$.

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

convergence studies
residual reduction analysis
runtime comparisons
error analysis
convergence plots for multiple grid resolutions

The experiments investigate the effect of preconditioning on convergence speed and scalability.

## Running the Project

Install the required packages:
pip install -r requirements.txt

Open the notebook:

jupyter notebook notebooks/helmholtz_iterative_solvers.ipynb

The solver can be selected inside the notebook by modifying the solver variable in the experiment configuration section.


de the notebook by modifying the solver variable in the experiment configuration se
