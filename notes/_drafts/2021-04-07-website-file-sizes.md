---
layout: post
title: "Optimizing image quality for my website"
subtitle: "Determining the optimal Lightroom settings when exporting photographs for my website"
background: /assets/img/posts/image_export_settings/web_export_settings.jpg
pagination: 
  enabled: true
category: notes
---
# Background

All the photographs on this website are taken by me. As such, it is up to me to optimize their file size *vs* quality when exporting. The majority of the photographs were taken with a Canon 5D Mark III so the exported full resolution jpeg files are usually around 12 MB in size. For reference, the photos that were included with this Jekyll theme were around 600 KB... 20 times smaller. 

# Goal

Find the optimal export settings to minimize the file size of a photograph without compromising image quality. Files will be optimized to be shown on a 4K monitor and 'portrait orientation' on mobile.

# Topics to Cover
There are a few aspects I consider when using Lightroom to export an image for my website:
1. DPI/PPI
2. Resolution
3. Quality
4. Masthead vs Body

# 1. DPI/PPI  
DPI stands for 'dots per inch.' When printing an image, this setting tells your printer how many dots of ink should be printed in every 1" of your image. PPI (pixels per inch) is a similar measurement of density, however instead of dots it refers to pixels per inch. However, your computer doesn't print the image to your screen, it simply displays the image per its set resolution. Compare the two images below. One is exported with a ppi of 1 and the other is exported with a ppi of 300. Can you tell the difference? Both images have a resolution of 600 x 400 and a file size of 279 KB. The first image is exported with a ppi of 1 and the second image is exported at a ppi of 300.

##### Note:
The images may be displayed off if you are viewing on mobile. I've hardcoded the images to display at their native resolution to give the most accurate representation of how dpi/ppi affects web images. I list the code used to display the images with hardcoded resolutions below the images.

![1 ppi](/assets/img/posts/image_export_settings/1_ppi.jpg){:width="600px" height="400px"} 

![300 ppi](/assets/img/posts/image_export_settings/300_ppi.jpg){:width="600px" height="400px"}



###### Code:
\!\[1 ppi](/img/website_file_size/1_ppi.jpg)<mark>{:width="600px" height="400px"}</mark>




# 2. Resolution  

An image 1920 x 1080 will always be 1920 pixels long and 1080 pixels wide. Any hardware/software magic your computer may preform to upscale an image, an image with a native resolution at 1920 x 1080 pixels displayed on a monitor with 3840 x 2160 resolution will not look as good as an the same image with a native resolution of 3840 x 2160.

Best, case scenario, the image will just not fill the entire screen, with the worst case being the image will be stretched to fill the screen to the point where you can start to see the individual pixels of the image. 
The masthead photos included in the [Jekyll theme](https://github.com/StartBootstrap/startbootstrap-clean-blog-jekyll) I am using had a resolution of around *1900 x 1200* or *2,280,000* pixels and a file size of around *600 KB*. As I have chosen to optimize for 4K resolution, *3840 x 2160* or *8,294,400* pixels (~**4x** the number of pixels), my target file size will be less than (600KB * **4**) =  *2400KB* or *2.4MB*.

# 3. Quality
When exporting in lightroom, you're given the option to adjust the 'quality' of the image from 1-100. I'll first compare the difference between 100 quality and 10 quality to get a good idea of what to look for as far as image degradation. Right click on the image and open in new tab to see it at its full resolution. To easily compare images use 'ctrl + Tab' and 'ctrl + Shift + Tab' to cycle through browser tabs quickly.

<!-- Row  -->
<div class="row"> 
  <!-- Column 1 -->
  <div class="col-lg-6 col-md-6">
    <figure class="image">
      <img style="width: 100%;" src="/assets\img\posts\image_export_settings\tree_100.jpg">
      <figcaption>Tree 100</figcaption>
    </figure>
  </div>
  <!-- Column 2 -->
  <div class="col-lg-6 col-md-6">
    <figure class="image">
      <img style="width: 100%;" src="/assets\img\posts\image_export_settings\tree_10.jpg">
      <figcaption>Tree 10</figcaption>
    </figure>
  </div>
</div>

<!-- Row  -->
<div class="row"> 
  <!-- Column 1 -->
  <div class="col-lg-6 col-md-6">
    <figure class="image">
      <img style="width: 100%;" src="/assets\img\posts\image_export_settings\sky_100.jpg">
      <figcaption>Sky 100</figcaption>
    </figure>
  </div>
  <!-- Column 2 -->
  <div class="col-lg-6 col-md-6">
    <figure class="image">
      <img style="width: 100%;" src="/assets\img\posts\image_export_settings\sky_10.jpg">
      <figcaption>Sky 10</figcaption>
    </figure>
  </div>
</div>

You can see obvious bands of color in the sky images as the color changes between different shades of blue. The tree image is less obvious to my eye but there is is definitly a reduction in sharpness.  

Below are examples of 10 cropped images with each reduced in quality by 10. I can't see myself cropping an image this much normally so this will test an edge-case. Images were exported with a 'long edge' of 1880px. 


<!-- Row  -->
<div class="row"> 
  <!-- Column 1 -->
  <div class="col-lg-6 col-md-6">
    <figure class="image">
      <img style="width: 100%;" src="/assets\img\posts\image_export_settings\100.jpg">
      <figcaption>Quality 100</figcaption>
    </figure>
  </div>
  <!-- Column 2 -->
  <div class="col-lg-6 col-md-6">
    <figure class="image">
      <img style="width: 100%;" src="/assets\img\posts\image_export_settings\90.jpg">
      <figcaption>Quality 90</figcaption>
    </figure>
  </div>
</div>

<!-- Row  -->
<div class="row"> 
  <!-- Column 1 -->
  <div class="col-lg-6 col-md-6">
    <figure class="image">
      <img style="width: 100%;" src="/assets\img\posts\image_export_settings\80.jpg">
      <figcaption>Quality 80</figcaption>
    </figure>
  </div>
  <!-- Column 2 -->
  <div class="col-lg-6 col-md-6">
    <figure class="image">
      <img style="width: 100%;" src="/assets\img\posts\image_export_settings\70.jpg">
      <figcaption>Quality 70</figcaption>
    </figure>
  </div>
</div>

<!-- Row  -->
<div class="row"> 
  <!-- Column 1 -->
  <div class="col-lg-6 col-md-6">
    <figure class="image">
      <img style="width: 100%;" src="/assets\img\posts\image_export_settings\60.jpg">
      <figcaption>Quality 60</figcaption>
    </figure>
  </div>
  <!-- Column 2 -->
  <div class="col-lg-6 col-md-6">
    <figure class="image">
      <img style="width: 100%;" src="/assets\img\posts\image_export_settings\50.jpg">
      <figcaption>Quality 50</figcaption>
    </figure>
  </div>
</div>

<!-- Row  -->
<div class="row"> 
  <!-- Column 1 -->
  <div class="col-lg-6 col-md-6">
    <figure class="image">
      <img style="width: 100%;" src="/assets\img\posts\image_export_settings\40.jpg">
      <figcaption>Quality 40</figcaption>
    </figure>
  </div>
  <!-- Column 2 -->
  <div class="col-lg-6 col-md-6">
    <figure class="image">
      <img style="width: 100%;" src="/assets\img\posts\image_export_settings\30.jpg">
      <figcaption>Quality 30</figcaption>
    </figure>
  </div>
</div>

<!-- Row  -->
<div class="row"> 
  <!-- Column 1 -->
  <div class="col-lg-6 col-md-6">
    <figure class="image">
      <img style="width: 100%;" src="/assets\img\posts\image_export_settings\20.jpg">
      <figcaption>Quality 20</figcaption>
    </figure>
  </div>
  <!-- Column 2 -->
  <div class="col-lg-6 col-md-6">
    <figure class="image">
      <img style="width: 100%;" src="/assets\img\posts\image_export_settings\10.jpg">
      <figcaption>Quality 10</figcaption>
    </figure>
  </div>
</div>

I started to see banding in the sky and a slight reduction in sharpness in the tree at around 40 quality. To my eye, the images at quality 100 compared to quality 50 are indiscernible. At 100 quality the image is 2.49 MB and at 50 quality the image is 623 KB. With a file size at around 4 times as small, the 50 quality looks to be good balance between file size and image quality. 

# 4. Masthead *vs* Body
There are two scenarios where images will be displayed:
1. In the Masthead
2. In the body of the post

In the masthead, the image bleeds all the way to the edge of the screen, which will require the image to be the full width of the monitor (3840px).
![Masthead](/assets\img\posts\image_export_settings\masthead.jpg){:width="100%"}

However in the body of the post, the image does not need to fill the entire width as there is white space on a 'landscape orientation' monitor. 

![white space](/assets\img\posts\image_export_settings\white_space.jpg){:width="100%"}

I order to know how large a 'body' image needs to be, I'll measure one of the white bars on the side, multiply by 2, and subtract that from the total horizontal resolution to obtain the width of the body. Here is a problem, my monitor is not 4K so I'm going to have to do some additional math to know how wide to make my images. Because I know that the width of my monitor (1920px) and a 4K Monitor (3840px)  are the same, I can multiply my calculation by 2 to obtain the final 4K resolution in the end.

Here, I used Photoshop to measure the white space on the left to be 490px. 

![size of white bar](/assets\img\posts\image_export_settings\size_of_white_bar.jpg){:width="100%"}

##### Calculations
Left + right bars = 980px. Total horizontal resolution (1920px) - Left and right bars (980px) = Size of body(940px).
Size of body (940px) * 4K size factor (2) = 1,880px

Below is an image exported with a width of 1880px. It looks great on my monitor, I'll need to confirm how it looks on a 4K monitor.
![1880px width](/assets\img\posts\image_export_settings\1880_width.jpg){:width="100%"}

# Conclusion
## DPI/PPI
DPI/PPI only matter when printing an image so it doesn't matter what this is set to.

## Resolution
Exporting a 'masthead' image is fairly straight forward in terms of resolution. The width of masthead images needs to be 3840px wide. 

Most of the 'body' images will have this bit of code at the end that forces the image to span the entire body of the site, regardless of the resolution of a monitor. This means that to optimize for 4K monitors, the width of a 'body' image needs to be 1880px wide.

## Quality

 The most efficient Lightrom 'quality' to export at is more subjective than 'resolution' and will differ between images. 

## Creating the Lightoom presets
I'll create two presets in Lightroom, one for the 'masthead web' and one for 'body web.' In the export box, I clicked 'Add' in the bottom left to add two presets and renamed them. Then I set the quality, resolution, format... etc, right clicked on the preset I wanted to assign those settings to and clicked "Update with Current Settings." Rinse and repeat for the other preset. 

![Lightroom Export Dialoge Box](/assets\img\posts\image_export_settings\export_box.jpg){:width="100%"}

Now, applying the proper export settings is as easy as 1 click!

# Future
Once I get some sort of analytics running, it would be nice to take some quantitative measurements on how quickly pages actually load.

# Additionally learned

#### Website actions

###### Start test server

bundle exec jekyll serve

###### Start test server displaying files in _drafts folder as posts

bundle exec jekyll serve --drafts

#### Images

###### Display two next to each other

\!\[1 ppi](/img/website_file_size/1_ppi.jpg){:width="49%"} \!\[300 ppi](/img/website_file_size/300_ppi.jpg){:width="49%"}

###### Specify pixel dim

\!\[small](/img/website_file_size/small.jpg){:height="36px" width="36px"}

###### Using html

\<img src="/img/website_file_size/small.jpg" alt="small" width="100px" height="300px"/> 

###### Highlight text using \<mark></mark>
<mark>{:width="600px" height="400px"}</mark>

###### Creating two columns in bootstrap
<!-- Row  -->
<div class="row"> 
  <!-- Column 1 -->
  <div class="col-lg-6 col-md-6">
    <figure class="image">
      <img style="width: 100%;" src="/assets\img\posts\image_export_settings\60.jpg">
      <figcaption>Quality 60</figcaption>
    </figure>
  </div>
  <!-- Column 2 -->
  <div class="col-lg-6 col-md-6">
    <figure class="image">
      <img style="width: 100%;" src="/assets\img\posts\image_export_settings\50.jpg">
      <figcaption>Quality 50</figcaption>
    </figure>
  </div>
</div>