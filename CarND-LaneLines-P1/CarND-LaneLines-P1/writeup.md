# **Finding Lane Lines on the Road** 

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My image processing pipeline consists of seven steps. First I create a copy of the image to work with. Next I apply a grayscale to the image. Then I apply Gaussian smoothing to the grayscale image before applying Canny edge detection. The Canny image is then used with a masking function to create a masked image displaying only the region of interest. Next I apply a Hough transform before returning the weighted image. 

A major part of the project was drawing single lines to represent the left and right lane lines. To do this I modified the provided draw_lines() function. To do this I created three additional functions: solve_line_equation_for_x(), extrapolate_line(), and calculate_avg_line(). Solve_line_equation_for_x(), extrapolate_line(), and calculate_avg_line are used with draw_lines() to extrapolate the averaged lines after applying the Canny and Hough functions. Draw_lines() then plots the new averaged and extrapolated lines on the image. 

### 2. Identify potential shortcomings with your current pipeline

I think there are several shortcomings with my current pipeline. One issue I encountered when processing the video files with my pipeline was that road curvature had an adverse effect on the accuracy of the drawn lines. I particularly noticed this with the second (yellow line) video clip. Another shortcoming is accuracy of my constants and parameters. I found it difficult to find find good values for all of the constants in the pipeline. 

### 3. Suggest possible improvements to your pipeline

As mentioned above I think that I could still continue to tune the constants in my image processing pipeline. Also, I think it could be made more robust to account for more varied road and environmental conditions. 
