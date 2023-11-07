# FootfallCam-AI-Evaluation-Test

## Environment
|Environment/Packages|	Version|
|----------------|------------|
|Windows|	11|
|python 	|3.8|
|jupyter notebook 	|6.5.2|
|openCV 	|4.5.2|
|numpy |	1.23.4|
|modelscope 	|1.9.4|

## Execute Code
run throught Human_Detection.ipynb file

## Project Introduction
Detect staff with name tag

## Solution
Using trained model in modelscope doing human head detection. Then using a fix constant to bound the name tag area relative with head detection result  
```relative_nametag_pos = [0, 10, 30, 20] #relative x0, y0, width, heigtht```

After that, using edge detection method in OpenCV2 (sobel filter)  ![image](https://github.com/Study-boy-dot/FootfallCam-AI-Evaluation-Test/assets/80616480/b7d1fca6-e023-45d6-973e-2ec27155216d). As the image shown, name tag of staff is black and white seems like easy to detect by edge detection method.

Edge detection result feed to find contour, using # contours to determine the area is name tag or not.

## Drawback
*	False classification happened
*	Nametag must be in a certain angle
*	Nametag detection depends on human head detection
*	Nametag position depends on human head position

## Future Work
* Fine-tuning model to increase the accuracy of model in a top-down view
* Using labelme to label video's frame and feed to small CNN to train
* Using trained CNN classifies name tag
