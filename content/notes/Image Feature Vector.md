A way to abstract information i.e. image, so that it's numerically quantifiable. Simply put, a list of numbers that represents an image. 

When building an image search engine, the first step is figure out what image descriptor to use. Am I trying to note a change in color, extract an object or differentiate between texture?
- This will handle the logic needed to represent our image as numbers

Assume we use raw pixel descriptor as our image descriptor.
- Basically, take all the pixels in an image and without any kind of processing, represent an individual pixel by it's color values (RGB, each channel is 0-255) or intensity (0-255)

A color mean and standard deviation descriptor would find the average and standard deviation of each channel of the image (so, each pixel's RGB values to form 3 numbers)
- Helps find the spatial distribution of color in an image!

A color histogram descriptor can also help tell us the distribution of colors in an image. If we divide the color space into discrete number of binds and then, count the number of pixels that fall into each bin, we have ourselves a color histogram.

