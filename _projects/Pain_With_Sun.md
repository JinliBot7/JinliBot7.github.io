---
layout: page
title: Paint With The Sun Project
description: 2021/07 - Now
img: /assets/img/SP_bg.png
importance: 1
category: On-going
---


<p align="center">
<img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/SP_exp.gif' | relative_url }}" alt="" title="example image"/>
</p>  

In this project, we developed a robotic system that automatically concentrates solar energy to a target point.

Check our latest video at: [Video](https://www.youtube.com/watch?v=HJ8wrbwiPDM).



The main components of the developed system are depicted below. The robotic system needs at least 5-DOF to achieve the aforementioned objective. To this end, we integrate a 3-DOF robotic arm Dobot Magician with two servo motors (controlled by a Raspberry Pi) to cooperatively manipulate a customized end-effector, which carries a spherical Fresnel lens, an RGB camera, and a thermal camera FLIR Lepton 3.5.

<div class="row">
    <div class="col">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/SP_system.png' | relative_url }}" alt="" title="example image"/>
    </div>
</div>

<div class="caption">
Set up.
</div>

We specifically design the structure of the end-effector so that the optical axis of the Fresnel lens and the optical axes of the two cameras intersect at the theoretical lens focal point, which creates a large overlapping of the FOVs of the two cameras. The pitch angle and the yaw angle of the lens are independently controlled by motor 1 and 2, while the 3-DOF translation of the lens is controlled by the robotic arm. Relying on the system kinematics, the distance between the lens center and an arbitrary target point can be set while maintaining the desirable pitch and yaw angles of the lens.

To regulate the position and energy density of the concentrated sunlight spot, we build a optics simulation of the Fresnel lens using Python.

<div class="row justify-content-sm-center">
    <div class="col-sm-6 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/SP_gif_azimuthal.gif' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm-6 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/SP_gif_polar.gif' | relative_url }}" alt="" title="example image"/>
    </div>
</div>






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
