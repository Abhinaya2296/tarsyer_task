# Annotation through Mouse-Click
# ROI
we will learn how to Graphically select a Region of interest (ROI) in an image and save it.
There are two functions which can be used to select ROI or ROIs in OPENCV.
“cv2.selectROI” which can be used to select a single ROI bounding box.
Selecting a single ROI is useful when you are sure you have to crop a single subject/ ROI from the image.
...
![Task_1](https://user-images.githubusercontent.com/82312119/189481125-528a3063-570f-4eba-9f91-64df4b1c3f3d.jpg)
...


Click and drag the mouse to make bounding box on the image . Press enter to finish selecting ROI and resume the program.

![crop](https://user-images.githubusercontent.com/82312119/189481138-988381c2-84b9-4a3e-ba3e-506774c815c9.jpeg)

# insights

![Task_1_insights](https://user-images.githubusercontent.com/82312119/189481156-1f3e3451-eae3-4387-b8e5-4a9fb2b5a037.jpg)


# Import the necessary libraries.
import cv2
import numpy

# Thresholding
Thresholding is a technique in OpenCV, which is the assignment of pixel values in relation to the threshold value provided. In thresholding, each pixel value is compared with the threshold value. If the pixel value is smaller than the threshold, it is set to 0, otherwise, it is set to a maximum value (generally 255). Thresholding is a very popular segmentation technique, used for separating an object considered as a foreground from its background. A threshold is a value which has two regions on its either side i.e. below the threshold or above the threshold. 
In Computer Vision, this technique of thresholding is done on grayscale images. So initially, the image has to be converted in grayscale color space.
#Syntax:
cv2.threshold(source, thresholdValue, maxVal, thresholdingTechnique) 
# Parameters: 
-> source: Input Image array (must be in Grayscale). 
-> thresholdValue: Value of Threshold below and above which pixel values will change accordingly. 
-> maxVal: Maximum value that can be assigned to a pixel. 
-> thresholdingTechnique: The type of thresholding to be applied. 

# Simple Thresholding
The basic Thresholding technique is Binary Thresholding. For every pixel, the same threshold value is applied. If the pixel value is smaller than the threshold, it is set to 0, otherwise, it is set to a maximum value.
The different Simple Thresholding Techniques are: 
 
cv2.THRESH_BINARY: If pixel intensity is greater than the set threshold, value set to 255, else set to 0 (black).
cv2.THRESH_BINARY_INV: Inverted or Opposite case of cv2.THRESH_BINARY.
![task3_simple_Binary Threshold](https://user-images.githubusercontent.com/82312119/189480885-9ebf1aac-a823-45e1-8a08-601a44ffd5d0.jpg)


# Adaptive thresholding
Adaptive thresholding is the method where the threshold value is calculated for smaller regions. This leads to different threshold values for different regions with respect to the change in lighting. We use cv2.adaptiveThreshold for this.
Syntax: cv2.adaptiveThreshold(source, maxVal, adaptiveMethod, thresholdType, blocksize, constant)

# Parameters:
-> source: Input Image array(Single-channel, 8-bit or floating-point)
-> maxVal: Maximum value that can be assigned to a pixel.
-> adaptiveMethod: Adaptive method decides how threshold value is calculated.

 cv2.ADAPTIVE_THRESH_MEAN_C: Threshold Value = (Mean of the neighbourhood area values – constant value). In other words, it is the mean of the blockSize×blockSize neighborhood of a point minus constant.
 ![task3_Adaptive Gaussian](https://user-images.githubusercontent.com/82312119/189480896-2fdd5e1c-3ba2-4f84-bf10-e817a25d73bc.jpg)

# Morphological Operation
# Erosion
Erosion is one of the most basic morphological operations. Erosion removes pixels on the boundaries of objects in an image, which will make the objects smaller.
![task2_erosion](https://user-images.githubusercontent.com/82312119/189480816-4bae805e-a73b-4a03-8fd8-4d21cc6851dd.jpg)

# Dilation
Dilation is the second most basic morphological operation. Dilation adds pixels on the boundaries of objects in an image, which will increase the size of objects in the image.
![task2_dilation](https://user-images.githubusercontent.com/82312119/189480829-13adcea5-4150-4156-baea-60028879adc5.jpg)

# Opening
A morphological opening is an erosion followed by a dilation. This operation is used to remove small objects and noise from an image.
![task2_opening](https://user-images.githubusercontent.com/82312119/189480840-0775ae05-3089-42e0-9d77-b5ff34f5cecf.jpg)

# hand-gesture-recognition-using-mediapipe

# Requirements
1)opencv-python
2)mediapipe


# MediaPipe

Simple Hand Gesture Recognition Code - Hand tracking - Mediapipe
Goal of this gist is to recognize B(baby fingure), T(thumb), M(middle),  R(ring fingure), I(index fingure). We use the LANDMARKS output of the Landmark. This output is a landmark list that contains 21 landmark. In the hand_landmarks.jpg picture below you can see the index of each landmark. Each landmark have x, y and z values. But only x, y values are sufficient for our Goal.
We have five finger states.
thumbIsOpen
firstFingerIsOpen
secondFingerIsOpen
thirdFingerIsOpen
fourthFingerIsOpen
For exmaple: thumb is open if the x value of landmark 3 and the x value of landmark 4 are less than x value of landmark 2 else it is close
![hand_landmarks](https://user-images.githubusercontent.com/82312119/189480949-6d67380e-4a27-4978-aba9-6da88c179222.png)

![hand_crops](https://user-images.githubusercontent.com/82312119/189480966-84e6dba9-b8f4-438f-a82e-8f9f4c8fe8cd.png)


# Reference
MediaPipe
https://google.github.io/mediapipe/solutions/hands.html
