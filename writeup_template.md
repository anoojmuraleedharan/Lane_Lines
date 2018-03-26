# **Finding Lane Lines on the Road** 


### Reflection

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I blurred the image using Gaussian smoothing so that it will be easier to detect edges in the resulting image. Then I applied Canny edge detection algorithm to get an edge detected image. This image is then masked to retain only the area I am interested in. Now to this image the Hough transform was applied to get the coordinated of the lines I am interested in.

And finally to draw a single line on the left and right lanes I modified the draw_lines() function by first finding out and seperating only those lines with a slope grater than 0.5. The lines having absolute slope grater than 0.5, thus obtained where seperated as those belonging to the right half and left half of the image. Then linear regression is used to find the best fit line for right and left lane lines. 



### 2. Identify potential shortcomings with your current pipeline

Though working pretty well with the test videos solidWhiteRight.mp4 and solidYellowLeft.mp4 the algorithm when applied to the challenge video and one other real time video collected by me shows imperfect lane lines with jitters and variations.


### 3. Suggest possible improvements to your pipeline
It might be suitable to add a colour filtering algorithm where it detects only the white and yellow pixels so that detecting of unwanted lines or edges and thereby avoiding the jitters and imperfections.


