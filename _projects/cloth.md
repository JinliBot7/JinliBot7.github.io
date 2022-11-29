---
layout: page
title: Differentiable Cloth Modeling
description: 2022/07 - now
img: /assets/img/simulation.png
importance: 1
category: On-going
---

<p>
<em>Updated on 2022/11/29</em>
</p>


I have implemented three types of cloth simulation methods, including

* Mass-Spring-System
* Finite Element Method
* Material Point Method

I use forward or symplectic Euler integration at this stage. Implicit integration may be implemented in the future. I found it is helpful to keep things simple at the beginning.

<h2> Mass-Spring-System </h2>
<p>
The Mass-Spring-System method is popular for real-time applications in robotics due to its simplicity. It models the deformable objects as a collection of particles connected by springs and dampers. However, the conciseness comes with the price of the lost of physical interpretability. It is not suitable for scenarios that involve large deformation, severe self-occulusion, and multiple material coupling. Here is an implementation in Taichi.
</p>

<p align="center">
  <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/cloth/1-mass-spring.gif' | relative_url }}"/>
</p>

<h2> Finite Element Method </h2>
<p>
The finite element method (FEM) is a numerical method for solving differential equations arising in engineering and mathematical modeling. Usually, the continuum material is discretized into triangular or tetrahedron elements. Then the deformation gradient and the internal stress are computed for each element. I tried to follow the classic 1998 SIGGRAPH paper <a href="https://www.cs.cmu.edu/~baraff/papers/sig98.pdf">"Large Steps in Cloth Simulation"</a>. A preliminary result is attached below. However, the self-collision was not handled properly and only the streching component of the energy density function was implemented. I didn't complete the full implementation since I found the result of the material point method (MPM), the state of the art method for deformbale object and granular particle simulation in the computer graphics community, is more promising. 
</p>  

<p align="center">
  <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/cloth_video.gif' | relative_url }}"/>
</p>

<h2> Material Point Method </h2>
A simple toy example of my MPM framework. Easy to debug.
<p align="center">
  <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/cloth/0-mpm-simple.gif' | relative_url }}"/>
</p>

Let's push a deformable sheet.

<p align="center">
  <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/cloth/2-push.gif' | relative_url }}"/>
</p>

Let's add the mesh indices and twist a deformable sheet. Green color represents det(F) > 1 and red represents det(F) < 1. Note that this is hard to achieve utilizing the traditional methods.
<p align="center">
  <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/cloth/t-1000.gif' | relative_url }}"/>
</p>

Change of the Young's modulus affect the twisting process.
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/cloth/t-100.gif' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/cloth/t-500.gif' | relative_url }}" alt="" title="example image"/>
    </div>  
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/cloth/t-1000.gif' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/cloth/t-3000.gif' | relative_url }}" alt="" title="example image"/>
    </div>  
</div>

<br>
I also did some experiments using a real peice of garment. 
<p align="center">
  <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/cloth/7-twist-real.gif' | relative_url }}"/>
</p>


<br>
Let's also shear a deformable sheet.
<p align="center">
  <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/cloth/s-2000.gif' | relative_url }}"/>
</p>

Change of the Young's modulus affect the shearing result.
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/cloth/s-100.gif' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/cloth/s-500.gif' | relative_url }}" alt="" title="example image"/>
    </div>  
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/cloth/s-1000.gif' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/cloth/s-2000.gif' | relative_url }}" alt="" title="example image"/>
    </div>  
</div>
<br>

I also did some experiments using a real peice of garment. 
<p align="center">
  <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/cloth/6-shear-real.gif' | relative_url }}"/>
</p>
<br>

Through the conducted experiments, I found that the twisting simulation was not so realistic. Espetially, the middle part of the garmment is much more bulky than the real one. After some analysis, I found the isotropic constitutive model caused the problem. Thus, I modified the deformation energy density function accroding to 2017 SIGGRAPH paper <a href="https://www.math.ucla.edu/~cffjiang/research/cloth/paper.pdf">"Anisotropic Elastoplasticity for Cloth, Knit and Hair Frictional Contact"</a>. The following shows the difference between the original and the improved simulation. Note that physical parameters are set the same and only the energy density function is different. The updated version on the right is closer the the real garment.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/cloth/8-twist-ori.gif' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/cloth/7-twist-real.gif' | relative_url }}" alt="" title="example image"/>
    </div>  
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/cloth/8-twist-improved.gif' | relative_url }}" alt="" title="example image"/>
    </div>  
</div>
<br>

I also started to develop my simulation playground in a more organized way. The cylinder shape static boundary is added with softened signed distance function (for a smoother gradient). Here are some preliminary results. 

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/cloth/9-drop0.gif' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/cloth/9-drop1.gif' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="row"> 
        <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/cloth/9-drop2.gif' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/cloth/9-drop4.gif' | relative_url }}" alt="" title="example image"/>
    </div>   
</div>
<br>

I recently found a promising related pioneer work <a href="http://plasticinelab.csail.mit.edu/">"PlasticineLab: A Soft-Body Manipulation Benchmark with Differentiable Physics"</a>. I decided to learn from it.

<h2> TO DO LIST </h2>
My next goal is to implement the moving boundary condition and the return mapping. 

I aslo attached two **wrong** implementations of the return mapping. It is hilarious how the material behaves. No one likes explosion except Deidara!
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/cloth/3-jiang1.gif' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/cloth/4-jiang2.gif' | relative_url }}" alt="" title="example image"/>
    </div>  
</div>
<br>


<h2> Reference Materials</h2>
* <a href="https://www.taichi-lang.org/">Taichi Lang</a>
* <a href="https://docs.taichi-lang.org/tgc01">Taichi Graphics Course</a>
* <a href="https://www.science.org/doi/10.1126/scirobotics.abd8803">Modeling, learning, perception, and control methods for deformable object manipulation</a>
* <a href="https://www.science.org/doi/10.1126/scirobotics.abm6010">Learning garment manipulation policies toward robot-assisted dressing</a>
* <a href="https://ieeexplore.ieee.org/document/9097275">A Grasping-Centered Analysis for Cloth Manipulation</a>
* <a href="https://www.math.ucla.edu/~cffjiang/research/mpmcourse/mpmcourse.pdf">The Material Point Method for Simulating Continuum Materials</a>








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
