---
layout: project
title: p0tat0
date: 23 November 2014
screenshot:
  src: /assets/img/projects/p0tat0/p0tat0@0.25x.jpg
  srcset:
    1920w: /assets/img/projects/p0tat0/p0tat0.jpg
    960w: /assets/img/projects/p0tat0/p0tat0@0,5x.jpg
    480w: /assets/img/projects/p0tat0/p0tat0@0,25x.jpg

image: '/assets/img/projects/p0tat0/sidebar-bg.jpg'
color: '#26002A'

caption: Abstract experiment in Blender
description: >
  This project was an abstract experiment in Blender aiming for a fractal-like 3D object, emulating the style of [David Zerba.](https://davidzerba.wordpress.com/tag/abstract/)
---

{% include archived.md %}

The original render, as seen below, was a simple Blender set-up consisting of only one light, the object, the background, and the camera, rendered with Cycles. IIRC the object was mostly lit by an HDR image (used to produce a more natural, global light than just Ambient Occlusion alone). I no longer have the HDR, which is why the .blend file included in the download has such a skewed color when rendered today. The focal blur was also done naturally in Blender with the virtual camera.

![Full-width image](/assets/img/projects/p0tat0/render.jpg){:.lead}

Post processing was done in Photoshop and consisted of a RGB shift, the purples on the side of the image, and the slight shading on the edges making a very subtle vignette. The RGB shift was simply a stylistic choice, where as the other effects where used to clean up and added to image, giving the illusion of a more sophisticated lighting setup.

*[IIRC]: If I remember correctly