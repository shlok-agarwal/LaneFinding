# **Finding Lane Lines on the Road** 

# Setup
       
I understand how virtual environments help battling system dependencies but I would encourage users to understand these version dependencies and set up their workflow.
For python 3.8 on a windows 64 bit system, these should help         
        
* Install 64 bit python because of a lot of packages are not available in 32 bit version 

```
python -m pip install --upgrade pip 
pip install scikit-learn scikit-image scipy  eventlet flask-socketio seaborn pandas ffmpeg imageio PyQt5 moviepy opencv-python requests keras jupyterlabPyQt5 
```
Tensor flow not available through pip for some reason. Install directly using wheels from [here](https://pypi.org/project/tensorflow/#files)

# Objective
**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road and visualize it.
* Reflect on your work in a written report

---

# Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

The Image processing pipleine in this project involves segmenting the given image to get the region of interest, then processing the image to identify lanes and lastly writing a function to overlay the lanes on the image.     
  
*Segmentation* : The region of interest can be any kind of polygon based on your application. A quadrangle worked best for this application.     
*Processing* : The image is first converted to gray scale, then run through a edge detector algorithm and lastly run through a line identifying algorithm.      
*Curve Fitting* : The lane lines are used to fit a polynomial curve.     


![lanes_1](https://user-images.githubusercontent.com/22652444/103008707-8d228400-4503-11eb-90c4-04929912ccbb.PNG)

![lanes_2](https://user-images.githubusercontent.com/22652444/103008797-ac211600-4503-11eb-9be3-94d897bc2342.PNG)
     
Modifications to the draw_line() function:             
* Need to segment the left and right lane. I found that by using the center line of the image, you can segment the left and right lanes. Alternatively the slope information of the lines can also be used.
* The points that form the lane lines can be fit into a higher order curve. This curve can be extrapolated to get a more continuous line.

### 2. Identify potential shortcomings with your current pipeline

With the limited time and scope of the project, this algorithm will work on straight lines and where the car is driving in the middle of two lanes. Detecting horizontal lines, lane crossings, lanes in peak traffic or different light conditions are part of the future work.

### 3. Suggest possible improvements to your pipeline

As future work, to improve the algorithm we can     
* Segment the Region of Interest, left and right lanes more smartly and not by hardcoding image vertices. Other scene or sensor information can be used for this.
* It would be better to use a higher order polynomial for curved lane lines. Need more careful parameter tuning for this to work. The current code facilitates this with `poly_order`.
