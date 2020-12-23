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

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I .... 

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by ...

If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
