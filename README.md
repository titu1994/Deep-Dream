# Deep Dream

Deep Dream modified implementation in Keras 1.0.6 using script provided at <a href="https://github.com/fchollet/keras/blob/master/examples/deep_dream.py">Deep Dream in Keras Examples</a>

## Examples
<img src="https://github.com/titu1994/Deep-Dream/blob/master/images/input/sky_clouds-wallpaper-1920x1080.jpg?raw=true" width=45% height=100%> <img src="https://github.com/titu1994/Deep-Dream/blob/master/images/output/Sky_at_iteration_5.png?raw=true" height=100% width=45%>

<img src="https://github.com/titu1994/Deep-Dream/blob/master/images/input/golden_gate.jpg?raw=true" height=100% width=45%> <img src="https://github.com/titu1994/Deep-Dream/blob/master/images/output/Golden_Gate_at_iteration_5.png?raw=true" height=100% width=45%>

## Weights (VGG 16)

Before running this script, download the weights for the VGG16 model at:
https://drive.google.com/file/d/0Bz7KyqmuGsilT0J5dmRCM0ROVHc/view?usp=sharing
(source: https://gist.github.com/baraldilorenzo/07d7802847aaad0a35d3)
and make sure the variable `weights_path` in this script matches the location of the file.

- Save the weights in the root folder
- Save a copy of the weights in the root of the windows_helper folder (if you wish to use the Windows Helper tool to easily execute the script)

## Windows Helper
It is a C# program written to more easily generate the arguments for the python script Network.py

- Make sure to save the vgg16_weights.h5 weights file in the windows_helper folder.
- Upon first run, it will request the python path. Traverse your directory to locate the python.exe of your choice (Anaconda is tested)

### Benefits 
- Automatically executes the script based on the arguments.
- Easy selection of images (Content, Style, Output Prefix)
- Easy parameter selection
- Easily generate argument list, if command line execution is preferred. 

## Parameters
```
--setting : Setting can be one of "bad_trip", "dreamy" or "custom" 
--iter : Number of iterations. Default is 5. Test the output with 5 iterations, and increase to improve results.

--continuity : If setting is custom, allows to select continuity factor
--dream_l2 : If setting is custom, allows to select dream_l2 factor
--jitter : If setting is custom, allows to select jitter factor
```

# Requirements 
- Theano
- Keras 
- CUDA (GPU)
- CUDNN (GPU)
- Scipy
- Numpy

# Speed
On a 980M GPU, the time required for each epoch depends on mainly image size (gram matrix size) :

At 600 x 600, each epoch requires 3 seconds.
