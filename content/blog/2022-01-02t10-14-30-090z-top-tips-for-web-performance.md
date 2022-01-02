---
createdAt: 2022-01-02T10:14:30.090Z
title: Top tips for web performance
description: Use srcset to automatically choose the right image size.
---
According to [HTTP Archive](https://httparchive.org/reports/state-of-images), a typical mobile web page weighs over 2.6 MB, and more than two thirds of that weight is images. That's a great opportunity for optimization!

![](https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/8A7JasX5JOADmB1XkjMC.svg "resp")

## tl;dr

* Don't save images larger than their display size
* Save multiple sizes for each image and use the [`srcset`](https://developer.mozilla.org/docs/Web/HTML/Element/img#attr-srcset) attribute to enable the browser to choose the smallest. The `w` value tells the browser the width of each version:

```html
<img src="small.jpg"\
srcset="small.jpg 500w,\
medium.jpg 1000w,\
large.jpg 1500w"\
alt="…">
```



## Save images with the right size [](https://web.dev/use-srcset-to-automatically-choose-the-right-image/#save-images-with-the-right-size)

You can make your website faster and less data hungry by using images with dimensions that match the display size. In other words, give images the right width and height when you save them.

Take a look at the images below.

They appear nearly identical, but the file size of one is more than 10 times larger than the other.

![Saved width 1000 px, file size 184 KB](https://web-dev.imgix.net/image/admin/IHpM8DG6qiNlRcbfxnt8.jpg?auto=format&w=845 "Saved width 1000 px, file size 184 KB")



![Saved width 300 px, file size 16 KB](https://web-dev.imgix.net/image/admin/XThwdsYxfx6KHkMxgbYI.jpg?auto=format&w=338 "Saved width 300 px, file size 16 KB")

The first image is much larger in file size because it's saved with dimensions much larger than the display size. Both images are displayed with a fixed width of 300 pixels, so it makes sense to use an image saved at the same size.

**For fixed widths, use images saved with the same dimensions as the display size.**