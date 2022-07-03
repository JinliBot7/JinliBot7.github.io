---
layout: page
title: Thermal Servoing Fundamentals
description: 2020/01-2021/10
img: /assets/img/TS_bg.jpeg
importance: 2
category: Past
---

<p align="center">
<img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/TS_video.gif' | relative_url }}" alt="" title="example image"/>
</p>  

For more details, please see our [paper](https://601318ff-63df-413d-983a-b8c13c4c1e60.filesusr.com/ugd/49b3f5_17bf17383fe94c7ea5c6b59d4d84ff64.pdf) and [video](https://www.youtube.com/watch?v=A0uWVN2cKwA).

Thermal servoing is a feedback control problem that deals with the regulation of an object’s temperature by means of motor actions of a rigid robot, which can either manipulate the object or the heat source. It is a frontier problem that
has numerous important applications (e.g., in industrial process control, cosmetic dermatology, fire-fighting missions, etc.) where temperature needs to be dynamically controlled and the environment is uncertain. The quality, performance, and safety of these (otherwise open-loop) applications can be improved by incorporating thermal sensorimotor capabilities.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/TS_illustration.png' | relative_url }}" alt="" title="example image"/>
    </div>
</div>

<div class="caption">
Creatures and robots with thermomotor intelligence: (a) When exposed to the sun, butterflies adjust their wings configuration to control their temperature; robotic systems with thermal servoing algorithms can be used for (b) firefighting, (c) volcano exploration, and (d) industrial applications.
</div>

Although thermal sensing is a mature technology and has a rich history in the automation of many tasks , its use as a feedback signal for robot control has not been sufficiently studied in the literature, where only a few works have addressed this challenging servo-control problem. However, in these previous methods, temperature control is achieved by directly modulating the power of the heat-generating components. This approach is not suitable when considering external heat sources, e.g., wildfires and sunlight, or when the source’s power should not be varied, e.g., in cosmetic procedures.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/TS_setup.png' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
Experimental setup for our radiation-based thermal servoing tests.
</div>

The dynamic coupling between temperature and motion may seem unintuitive for humans, whereas many organisms extensively exploit these relations. Such advanced thermoception-based behaviors can be used to solve many real-world problems. However, these advanced thermoception-based capabilities have not yet been fully incorporated in robot control, a discipline with good track record of borrowing inspiration from nature, but which seems to be lagging in this direction. As a feasible solution to the aforementioned issues, in this article, we present a rigorous formulation for robot thermal servoing with radiative sources.

Here are the results of the experiments in which the adaptive controller is applied to regulate the temperature of the three objects.
<p align="center">
<img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/TS_exp_plots.png' | relative_url }}" alt="" title="example image"/>
</p>  


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


<div class="row justify-content-sm-center">
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
