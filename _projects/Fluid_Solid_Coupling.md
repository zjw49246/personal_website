---
layout: page
title: Fluid Solid Coupling
description: Implementation of fluid solid coupling
img: assets/img/fluid_solid_coupling.gif
importance: 1
category: Computer Graphics
github: https://github.com/zjw49246/Fluid_Solid_Coupling
tag1: Physics-based Simulation
tag1_style: info
---

&nbsp;&nbsp;&nbsp;&nbsp;This project implemented the algorithm in <a href="https://dl.acm.org/doi/abs/10.1145/1276377.1276502">A Fast Variational Framework for Accurate Solid-Fluid Coupling</a>. The simulation results are shown in Figure 1.

&nbsp;&nbsp;&nbsp;&nbsp;When solving the pressure which enforces the velocity field to be divergence free, this algorithm doesn't discretize PDE with boundary conditions, which can be tricky at non-grid-aligned boundaries. Instead, it relies on the estimation of the whole system's kinetic energy. Assuming the system stays at the state with minimum energy, the pressure field $$\textbf{p}$$ can be computed by solving
$$
\begin{equation}
\frac{\Delta t}{\rho^2}\textbf{G}^T\textbf{M}_F\textbf{Gp} + \Delta t\textbf{J}^T\textbf{M}_S\textbf{J} = \frac{1}{\rho}\textbf{G}^T\textbf{M}_F\textbf{u} - \textbf{J}^T\textbf{V}^n
\end{equation}
$$
where $$\textbf{G}$$ is the gradient finite difference operator, $$\textbf{M}_F$$ and $$\textbf{M}_S$$ are the mass matrix of fluid and solid respectively, $$\textbf{J}$$ is the operator mapping pressure to net force and torgue on the solid, $$\textbf{u}$$ is the fluid velocity field and $$\textbf{V}^n$$ is the (translational and angular) velocity of the solid.

&nbsp;&nbsp;&nbsp;&nbsp;We use Jacobi iterations to solve this equation. Due to the large size of the matrices $$\textbf{G}^T\textbf{M}_F\textbf{Gp}$$ and $$\textbf{J}^T\textbf{M}_S\textbf{J}$$, they are stored and computed in sparse form.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/fluid_solid_coupling.gif" title="Figure 1" class="img-fluid rounded z-depth-1 mx-auto d-block" %}
    </div>
</div>
<div class="caption">
    Figure 1: Fluid Solid Coupling
</div>