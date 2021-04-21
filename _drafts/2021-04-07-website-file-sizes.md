---
layout: post
title: "Optimizing image quality for my website"
subtitle: "Determining the optimal Lightroom settings when exporting photographs for my website"
background: /assets/img/posts/Rajio_Taiso/4S0A0496.jpg
pagination: 
  enabled: true
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
The images may be displayed off if you are viewing on mobile. I've hardcoded the images to display at their native resolution to give the most accurate representation of how dpi/ppi affects web images. I list the code used to display the images with hardcoded resolution below the images.

![1 ppi](/assets/img/posts/image_export_settings/1_ppi.jpg){:width="600px" height="400px"} ![300 ppi](/assets/img/posts/image_export_settings/300_ppi.jpg){:width="600px" height="400px"}

###### Code:
\!\[1 ppi](/img/website_file_size/1_ppi.jpg)<mark>{:width="600px" height="400px"}</mark>




# 2. Resolution  

An image 1920 x 1080 will always be 1920 pixels long and 1080 pixels wide. Any hardware/software magic your computer may preform to upscale an image, an image with a native resolution at 1920 x 1080 pixels displayed on a monitor with 3840 x 2160 resolution will not look as good as an the same image with a native resolution of 3840 x 2160.

 Best, case scenario, the image will just not fill the entire screen, with the worst case being the image will be stretched to fill the screen to the point where you can start to see the pixels of the image. 
The masthead photos included in the [Jekyll theme](https://github.com/StartBootstrap/startbootstrap-clean-blog-jekyll) I am using had a resolution of around *1900 x 1200* or *2,280,000* pixels and a file size of around *600KB*. As I have chosen to optimize for 4K resolution, *3840 x 2160* or *8,294,400* pixels (~**4x** the number of pixels), my target file size will be less than (600KB * **4**) =  *2400KB* or *2.4MB*.

# 3. Quality  
When exporting in lightroom, I'm given the option to adjust the 'quality' of the image from 1-10.

# 4. Masthead *vs* Body
There are two scenarios where images will be displayed:
1. In the Masthead
2. In the body of the post

In the masthead, the image bleeds all the way to the edge of the screen, which will require the image to be the full width of the monitor (3840px).
![Masthead](/assets\img\posts\image_export_settings\masthead.jpg){:width="100%"}

However in the body of the post, the image does not need to fill the entire width as there is white space on a 'landscape orientation' monitor. 

![white space](/assets\img\posts\image_export_settings\white_space.jpg){:width="100%"}

# Conclusion
Exporting a masthead image is fairly straight forward in terms of resolution. The width of masthead images needs to be 3840px wide. The quality 
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
