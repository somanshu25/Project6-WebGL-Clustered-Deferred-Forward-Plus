WebGL Clustered and Forward+ Shading
======================

**University of Pennsylvania, CIS 565: GPU Programming and Architecture, Project 5**

* SOMANSHU AGARWAL
  * [LinkedIn](https://www.linkedin.com/in/somanshu25/)
* Tested on: (TODO) **Google Chrome 222.2** on
  Windows 22, i7-2222 @ 2.22GHz 22GB, GTX 222 222MB (Moore 2222 Lab)

### Live Online

[![](img/thumb.png)](http://TODO.github.io/Project5B-WebGL-Deferred-Shading)

### Demo Video/GIF

![](vedio2.gif)

### Table of Contents

1. [Introduction](#Introduction)
2. [Forward Plus](#Forward-Plus)
3. [Clustering](#CLustering)
4. [Effects](#Effects)
5. [Optimization](#Optimization)
6. [Analysis] (#Analysis)
7. [Bloopers] (#Bloopers)
8. [References](#References)
9. [Credits] (#Credits)

### Introduction
In this project, we will be performing analysis of three rendering techniques, forward, forward plus and clusgtering (using deferred). I will be also performing some of the lightning effect such as Blinn Phong lightning model and also tried to perform the optimization by using two slots int eh texture buffer instead of three by saving the normal 2-components.

### Forward Plus
In the forward rendering technique, we go over all the light sources and then loop over all the object geometries and then check whether the light has an impact on the geometry adn then shade the point/geometry according to it. In forward plus, we divide the screen in tiles of same size. Hence, we get tiles in the shape of frustum in which the light source will lie. FOr each frustum tile, we will be storing the corresponding number of lights impacted and the list of light indices. AFter performing this, for the geometry lying in the space, we calculate the frustum it les and loop over those lights only, rather than the total number of lights, giving us performance improvement.

### Clustering

Here, we reuse the forward plus logic of storing the lights for eahc frustum and we stor the geometry related data (posirtion, normal and color of the point) in the g-buffer (geometry buffer) and then use the data when the geometry is called and then loop over the lights. Here, we are not looping all over the geometries in case of previous techniques.

### Effects


### Credits

* [Three.js](https://github.com/mrdoob/three.js) by [@mrdoob](https://github.com/mrdoob) and contributors
* [stats.js](https://github.com/mrdoob/stats.js) by [@mrdoob](https://github.com/mrdoob) and contributors
* [webgl-debug](https://github.com/KhronosGroup/WebGLDeveloperTools) by Khronos Group Inc.
* [glMatrix](https://github.com/toji/gl-matrix) by [@toji](https://github.com/toji) and contributors
* [minimal-gltf-loader](https://github.com/shrekshao/minimal-gltf-loader) by [@shrekshao](https://github.com/shrekshao)
