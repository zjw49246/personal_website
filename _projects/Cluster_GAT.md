---
layout: page
title: Eﬃcient Graph Attention Networks (GAT)
description: Acceleration of GAT
img: assets/img/Cluster_GAT.png
importance: 1
category: Machine Learning
tag1: Graph Neural Networks
tag1_style: info
---

Graph attention networks (GAT) are graph neural networks based on attention mechanism. Although it performs well on many graph datasets, it suffered from the problem that its training time is too long. In this project, we replaced the original attention layer in GAT with linear attention layer to reduce the time complexity of training. 

In addition, the neighbors of different nodes are usually different in GAT, so every time we do attention we can get the new feature of only one node, which affects the training speed. Inspired by Cluster-GCN, we clustered the nodes according to connectivity among them in the preprocessing step. Then we assumed all the nodes in the same cluster are neighbors of each other, which means we deleted all the edges in the edge and added edges between nodes in the same cluster (See Figure 1). We do attention in each of the cluster, and we can generate the new features of all the nodes in the cluster after one execution of attention. In this way, we can further accelerate the training of GAT.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Cluster_GAT.png" title="Figure 1" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure 1: Cluster nodes and modify edges
</div>