# **Finding Lane Lines on the Road** 



---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./test_images_output/gray.png "Grayscale"
[image2]: ./test_images_output/Canny.png "Edges"
[image3]: ./test_images_output/out3.png "Rawlines"
[image4]: ./test_images_output/out4.png "output"

---

### Reflection

### 1. Pipeline

My pipeline consisted of the following steps.... 

i)Conversion of the image to grayscale.

![alt text][image1]

ii) Guassian filter to smoothen the image with a kernel size 5

iii)Canny edge Detection

![alt text][image2]

iv)Define Region of Interest

v)Hough transform to identify the lines that constitute left and right lanes. Since some frames return a Zero Division Error I have defined 2 sets of parameters to tackle that exception.

vi)Superimpose the Lane Lines drawn onto the original image

![alt text][image3]


vii)In order to draw a single line on the left and right lanes, I modified the draw_lines() function by assigning lines produced from the hough transform to left and right lane arrays based on the slope of the line. Then I calculated the x-intercept of each line. I calculated the average of the slopes and Intercepts of the left and right lane lines. Then I used the equation y=mx+c to draw the lane lines given their boundaries.

![alt text][image4]



### 2. Potential shortcomings with your current pipeline


One potential shortcoming would be that it wouldnt work with curved roads i.e Roads with sharp turns

Another shortcoming could be sharp changes in the slope of the lane lines from one frame to another, instead of a gradual change.


### 3. Possible improvements to your pipeline

A possible improvement would be to average out the slopes of the lines of the previous frames to provide a more stable plot.

Another potential improvement could be to make it robust enough to work on curved roads.
