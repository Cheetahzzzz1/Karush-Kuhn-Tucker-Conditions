# Karush Kuhn Tucker Conditions

# Overview

This project solves a constrained entropy maximization problem using both primal and dual formulations. The objective is to verify strong duality and the optimality of the solution by checking the Karush-Kuhn-Tucker conditions.

# Problem Statement

We are given the following optimization problem :

Minimize : $f_0(x) = \sum_{i=1}^{n}x_{i}log(x_{i})$

Subject To :

-> $Ax <= b$

-> $1^T = 1$

-> $x \epsilon R^{n}_{++}$

For this assignment :

$$
A = \begin{bmatrix}
4 & 0.9 & 2 \\
1.3 & 0.6 & 6
\end{bmatrix}
$$

$$
b = \begin{bmatrix}
1.2 \\
0.8
\end{bmatrix}
$$

$$
n = 3
$$

# Part (a) - Primal Problem

We use cvxpy to solve the entropy maximization problem. Since entropy is concave, we maximize $\sum entr(x_i)$, which is equivalent to minimizing 
$\sum x_ilog(x_i)$.

<ins> Output </ins>

1. Optimal $x^*$: [0.08766, 0.88666, 0.02567]

2. Primal optimal value: -0.4141

# Part (b) - Dual Problem

We Solve the dual formulation:

Maximize 
