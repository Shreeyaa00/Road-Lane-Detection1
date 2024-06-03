# Road Lane Detection
When driving, we rely on our eyes to determine the direction and use the road lines as a constant reference for steering the vehicle. Similarly, in developing a self-driving car, a key initial step is to create an algorithm that can automatically detect lane lines. This project proposes a line detection algorithm to identify lane lines in images using Python and OpenCV. OpenCV, which stands for "Open-Source Computer Vision," is a package offering many valuable tools for image analysis. Detecting lane markings on roads can be achieved through established computer vision techniques.

## Problem Statement
The objective is to be able to detect lane lines in images and videos real-time. Images present various difficult levels with varying levels of shade, solid and dotted lines, of different colors and various x-y dimensions. A sample of the training set is shown below.

![solidYellowCurve](https://github.com/Shreeyaa00/Road-Lane-Detection1/assets/168258591/d0d8b2b9-0fd4-4999-be4b-75b4fa16347c)
![solidWhiteCurve](https://github.com/Shreeyaa00/Road-Lane-Detection1/assets/168258591/27935a7f-d64a-4a06-9370-78db40771b9d)


## converting the image into GrayScale
First, we need to clear the noise in the image because it may create false noise which might affect the edge detection. 
Filtering and Smoothing can be done by Gaussian Blur.

## To smooth the image
Image can be made smooth by modifying the value of a pixel by average value of the pixel intensifies around the target pixel.

## Applying Canny to identify Edges
The change of brightness over a series of pixels is GRADIENT. Strong gradient indicates a steep change and a shallow change.
By computing the derivatives in all directions of the image we are computing the Gradient , Since we call gradient as a change in intensity of pixels
If the gradient is larger than the upper threshold then it is accepted as a edge pixel, if it is below the lower threshold then it is rejected , if the gradient is between the upper and lower thrrshold then it will accepted if it is conneted to a stronger threshold.

Gradients that exceed the high_threshold are traced as bright pixels, identifying the adjacent pixels in the image with the most rapid changes in brightness, small changes in brightness are not traced and accordingly they are black as they fall below the lower threshold
We used Canny Method  to outline the strongest gradient in our Image.
![Canny_image](https://github.com/Shreeyaa00/Road-Lane-Detection1/assets/168258591/0e63974c-076c-46eb-8544-742817bd4f47)

## Identifying Lane Lines in the Image
Before we detect. Firstly, we need to decide a particular lanes in the image that we should work-on to write the program.
we use the function region_of_interest(): returns the enclosed region of our field of view.

## Hough Transform
This technique helps to detect the stright lines in the image and helps indentifing Lane lines.

![output](https://github.com/Shreeyaa00/Road-Lane-Detection1/assets/168258591/ecd6383d-07e1-49c0-8ad9-463e54c6f307)


https://github.com/Shreeyaa00/Road-Lane-Detection1/assets/168258591/1dafd002-c9bc-4306-bf11-0acd73ab188d


