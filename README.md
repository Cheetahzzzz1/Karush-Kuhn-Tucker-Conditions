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

Maximize : $(-b)^T\lambda - log(\sum^{n}_{i=1} e^{(-a)^{T}\lambda})$

Subject To : $\lambda >= 0$

<ins> Output </ins>

1. Optimal $\lambda^{*}$ : [0.62717, 0.52817]

2. Dual optimal value : -0.4141

This matches the primal result, confirming strong duality.

# Part (c) - KKT Conditions Verification

We validate the following conditions:

<ins> 1. Primal Feasibility:</ins>

$Ax^* \leq b,\ \sum x_i^* = 1$

<ins> 2. Dual Feasibility:</ins>

$\lambda^{*} >= 0$

<ins> 3. Stationarity:</ins>

$\nabla f_0(x) + A^T \lambda + \nu \mathbf{1} = 0$

All components of $\nu^*$ are approximately -1.76105.

<ins> 4. Complementary Slackness:</ins>

$\lambda_i (A x - b)_i = 0$

Products are near zero: [6.27e-10, 7.92e-9]

All Conditions are satisfied, confirming optimality of the solution.

# Tools Used

1. Python 3.10

2. **cvxpy** for convex optimization.

3. **scipy.optimize** for solving the dual problem.

4. **numpy** for matrix operations.

# Conlusion

The primal and dual solutions match, confirming strong duality. all KKT conditions are satisfied, verifying that the computed solutions are optimal for the entropy maximization problem under the given constraints.
