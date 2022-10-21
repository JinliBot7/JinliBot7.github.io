---
layout: page
title: Differentiable Cloth Modeling
description: 2022/07 - now
img: /assets/img/cloth.png
importance: 1
category: On-going
---

<p style="color:gray;">
A part of the following content is rephrased from this <a href="https://www.diva-portal.org/smash/get/diva2:1576162/FULLTEXT01.pdf">paper</a>. This <a href="https://www.science.org/doi/abs/10.1126/scirobotics.abm6010">paper</a> and this <a href="https://ieeexplore.ieee.org/document/9097275">paper</a> are also comprehensive materials to start with. For implementation, if you are also using Taichi, <a href="https://github.com/taichi-dev/taichi">Ti examples</a> are always a good starting point.</p>

<h2> Mass-Spring-System </h2>
<p>
There are three main streams of cloth modeling techniques. The Mass-Spring-System method is the most popular for real-time applications in robotics due to its simplicity. It models the deformable objects as a collection of particles connected by springs and dampers. However, the conciseness comes with the price of the lost of physical interpretability. It is not suitable for scenarios that involve large deformation, sever self-occulusion, and multiple material coupling. Here is an implementation.
</p>


<p>
My first simulation based on 1998 SIGGRAPH paper <a href="https://www.cs.cmu.edu/~baraff/papers/sig98.pdf">"Large Steps in Cloth Simulation"</a>. I attempt to use MPM for the next project. 
</p>  
<img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/cloth_video.gif' | relative_url }}" alt="" title="example image"/>









<!-- <div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/1.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/3.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/5.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    Caption photos easily. On the left, a road goes through a tunnel. Middle, leaves artistically fall in a hipster photoshoot. Right, in another hipster photoshoot, a lumberjack grasps a handful of pine needles.
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/5.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    This image can also have a caption. It's like magic.
</div>

You can also put regular text between your rows of images.
Say you wanted to write a little bit about your project before you posted the rest of the images.
You describe how you toiled, sweated, *bled* for your project, and then... you reveal it's glory in the next row of images.


<div class="row justi

Alt Textfy-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/6.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/11.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    You can also have artistically styled 2/3 + 1/3 images, like these.
</div> -->


<!-- The code is simple.
Just wrap your images with `<div class="col-sm">` and place them inside `<div class="row">` (read more about the <a href="https://getbootstrap.com/docs/4.4/layout/grid/">Bootstrap Grid</a> system).
To make images responsive, add `img-fluid` class to each; for rounded corners and shadows use `rounded` and `z-depth-1` classes.
Here's the code for the last row of images above:

```html
<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/6.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/11.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
``` -->
