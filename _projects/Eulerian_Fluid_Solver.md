---
layout: page
title: Eulerian Fluid Solver
description: Implementation of a Eulerian fluid solver, which supports MacCormack advection, conjugate gradients iteration and MGPCG
img: assets/img/eulerian_fluid_solver/non_test_mode.gif
importance: 2
category: Computer Graphics
github: https://github.com/zjw49246/Eulerian_Fluid_Solver
tag1: Physics-based Simulation
tag1_style: info
---

&nbsp;&nbsp;&nbsp;&nbsp;This project extended the Eulerian fluid solver in <a href="https://github.com/taichi-dev/taichi/blob/master/python/taichi/examples/simulation/stable_fluid.py">taichi's stable fluid example</a> which uses semi-Lagrangian advection and Chorin-style projection with Jacobi iteration. The extention includes MacCormack advection, conjugate gradients iteration with Jacobi preconditioner and multigrid preconditioner (MGPCG). The implementation of MGPCG is based on <a href="https://www.math.ucla.edu/~jteran/papers/MST10.pdf">A Parallel Multigrid Poisson Solver for Fluids Simulation on Large Grids</a>. The simulation results of different iteration methods and iteration numbers are shown in Figure 1 - 4.

&nbsp;&nbsp;&nbsp;&nbsp;We can see that the performance of 20 times Jacobi iteration is not good, while 20 times conjugate gradients iteration and MGPCG performs well. After increasing the number of iterations to, Jacobi iteration can achieve similar performance to the other two methods.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/eulerian_fluid_solver/results_jacobi_20_test_mode.gif" title="Figure 1" class="img-fluid rounded z-depth-1 mx-auto d-block" %}
    </div>
</div>
<div class="caption">
    Figure 1: Jacobi Iteration (20 times)
</div>



<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/eulerian_fluid_solver/results_jacobi_500_test_mode.gif" title="Figure 1" class="img-fluid rounded z-depth-1 mx-auto d-block" %}
    </div>
</div>
<div class="caption">
    Figure 2: Jacobi Iteration (500 times)
</div>



<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/eulerian_fluid_solver/results_cg_20_test_mode.gif" title="Figure 1" class="img-fluid rounded z-depth-1 mx-auto d-block" %}
    </div>
</div>
<div class="caption">
    Figure 3: Conjugate Gradients Iteration with Jacobi Preconditioner (20 times)
</div>



<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/eulerian_fluid_solver/results_mgpcg_20_test_mode.gif" title="Figure 1" class="img-fluid rounded z-depth-1 mx-auto d-block" %}
    </div>
</div>
<div class="caption">
    Figure 4: MGPCG (20 times)
</div>


