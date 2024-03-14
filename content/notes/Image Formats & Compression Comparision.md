---
title: Image Formats & Compression Comparision
tags:
  - Areas
  - completed
---
Digital graphic files will generally fall into two categories:
1. Raster graphics are created using a grid of tiny pixels, making them very simple
2. Vector graphics are creating using detailed paths of points & lines to render images. 

The simplest format begins with a bitmap, .bmp extension. It's the truest image where it stores every pixel (i.e. Raster file type), it's lossless and uncompressed. 

JPEG, Joint Photographic Experts Group, solves the issue of large file sizes and are great for images with gradients. 
- 'Lossy' bitmap format: To maintain small file size, some information of the image is discarded. Saving at maximum quality maximizes as much image quality as possible.
- JPEG Artefacts are result of an aggressive data compression result or conversion between different formats. This is especially noticeable in images with sharp lines, or sharp contrast between two colours. 

Resource: [Mathematics behind JPEG](https://cuhkmath.wordpress.com/2012/10/06/mathematics-behind-jpeg/)
The Fourier coefficients indicate how the function oscillates. So, if a function is close to a constant value, the Fourier coefficients of that function decay very fast. So, just with the first few terms of the Fourier series, we will be close to the original function. 

How can we use this property to store images efficiently in JPEG format?
- Calculate the Fourier coefficients of an image (i.e. perform a 2D Fourier Transform on the image to represent in frequency domain).
In python, this can be achieved by:
``` python
import numpy as np
f_transform = np.fft.fft2(image)
```
- Store the first few big Fourier coefficients, discard the small, high-frequency coefficients
It's also why JPEG does not work well with storing text - there is a big change in background colour and text colour. These are big coefficients with high frequency, and discarding this information leads to JPEG artefacts.

PNG, which contrary to JPEG, they render sharp contrasts better than gradients by being more smarter with how they store image. It's a raster file format, lossless and smaller file size. 

How does it compress images? 
It compares individual pixels with neighbouring pixels. If they are of the same color, it compresses this information.

SVG, Scalable Vector Graphics, is a vector graphic file which stores the instructions on how to draw. These are impossible for photos, but nice for logos or simpler images.