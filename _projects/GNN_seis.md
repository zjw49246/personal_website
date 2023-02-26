---
layout: page
title: Earthquake Location with GNN
description: Predict earthquakes' locations with GraphSage
img: assets/img/GNN_seis/model.png
importance: 1
category: Machine Learning
report: ../assets/reports/GNN_seis.pdf
tag1: Graph Neural Networks
tag1_style: info
tag2: Seismology
tag2_style: warning
---

Earthquake Location is a very important problem in seismology, which is aimed to compute the location of seismic sources from the data recorded at seismic stations or geophones. However, traditional methods of earchquake location is costly, and requires manual work of picking seismic waves' first arrivals and the velocity model of underground structures. In recent years, deep learning techniques are applied to earchquake location which partially solves problems mentioned above. But in these methods, the location information are not fully captured, which affects the accuracy of the output location. Therefore, we propose a new method which uses graph neural networks to do earchquake location.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/GNN_seis/model.png" title="Figure 1" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure 1: Model Architecture
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/GNN_seis/source_geophone.png" title="Figure 2" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure 2: Geophones and Seismic Sources
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/GNN_seis/results_3d.png" title="Figure 3" class="img-fluid rounded z-depth-1 mx-auto d-block" %}
    </div>
</div>
<div class="caption">
    Figure 3: 3D Results
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/GNN_seis/results_2d.png" title="Figure 2" class="img-fluid rounded z-depth-1 mx-auto d-block" %}
    </div>
</div>
<div class="caption">
    Figure 4: 2D Results
</div>
