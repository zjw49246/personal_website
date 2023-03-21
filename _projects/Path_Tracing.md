---
layout: page
title: Path Tracing Renderer 
description: Implementation of path tracing with Monte Carlo integration, BVH and light sampling
img: assets/img/path_tracing.jpg
importance: 4
category: Computer Graphics
tag1: Rendering
tag1_style: primary
---

<script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
<script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>

&nbsp;&nbsp;&nbsp;&nbsp;This project implemented a path tracing renderer. The path tracing algorithm uses Monte Carlo integration (See Eq.(1)) to numerically calculate the radience of a shading point. 

$$
\begin{equation}
\begin{aligned}
L_o(p, \omega_o) &= \int_{\Omega^+}L_i(p, \omega_i)f_r(p, \omega_i, \omega_o)(n\cdot\omega_i)d\omega_i \\
                 &\approx \frac{1}{N}\sum_{i=1}^N\frac{L_i(p, \omega_i)f_r(p, \omega_i, \omega_o)(n\cdot\omega_i)}{p(\omega_i)},
                 \omega_i \sim p(\omega)
\end{aligned}
\end{equation}
$$

&nbsp;&nbsp;&nbsp;&nbsp;The path tracing algorithm requires computing the intersection between ray and objects in the secne, which is very costly when the number of objects (e.g. meshes constructing walls) is very large. To accelerate the intersection computation, all the obejects are divided into bouding boxes and forms bounding volume hierarchy (BVH). Therefore, the ray can hierarchically intersects with a few number of objects.

&nbsp;&nbsp;&nbsp;&nbsp;In addition, to improve the efficiency of the sampling in Monte Carlo integration, light sampling is used to replace the uniform sampling of all directions.

&nbsp;&nbsp;&nbsp;&nbsp;The rendering result of Cornell box scene is shown in Figure 1.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/path_tracing.jpg" title="Figure 1" class="img-fluid rounded z-depth-1 mx-auto d-block" %}
    </div>
</div>
<div class="caption">
    Figure 1: Rendering results of Cornell box
</div>