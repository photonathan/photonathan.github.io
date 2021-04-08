---
layout: post
title: "Optimizing image quality for my website"
subtitle: "Determining the optimal Lightroom settings when exporting photographs for my website"
background: /assets/img/posts/Rajio_Taiso/4S0A0496.jpg
pagination: 
  enabled: true
---
## Background

All the photographs on this website are taken by me. As such, it is up to me to optimize their file size vs quality when exporting. The majority of the photographs were taken with a Canon 5D Mark III so the exported jpeg files can be around 12MB in size. For reference, the photos that were included with this Jekyll theme were around 600KB... 20 times smaller. 

## Goal

Find the optimal export settings to minimize the file size of a photograph without compromising image quality. Files will be optimized to be shown on a 4K monitor.


There are a few aspects I consider when using Lightroom to export an image for my website:
1. DPI
2. Resolution
    The masthead photos included in the [Jekyll theme] (https://github.com/StartBootstrap/startbootstrap-clean-blog-jekyll) I am using had a resolution of around 1900 x 1200 or 2,280,000 pixels and a file size of around 600KB. As I have chosen to optimize for 4K resolution, 3840 x 2160 or 8,294,400 pixels (~4x the number of pixels), my target file size will be less than (600KB * 4) =  2400KB or 2.4MB.
3. Quality  
  
### Note
Once I get some sort of analytics running, it would be nice to take some quantitative measurements on how quickly pages actually load.

