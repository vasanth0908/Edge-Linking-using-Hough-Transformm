# Edge-Linking-using-Hough-Transformm
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:

Import all the necessary modules for the program.
### Step2:

Load a image using imread() from cv2 module.
### Step3:

Convert the image to grayscale.
### Step4:

Using Canny operator from cv2,detect the edges of the image.
### Step5:

Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.
### Developed by : vasanth s
### Reg no : 212222110052

### Input image and grayscale image
```
import numpy as np
import cv2
import matplotlib.pyplot as plt
img=cv2.imread("aizen.png",0)
img_c=cv2.imread("aizen.png",1)
img_c=cv2.cvtColor(img_c,cv2.COLOR_BGR2RGB)
gray=cv2.cvtColor(img,cv2.COLOR_GRAY2RGB)
gray = cv2.GaussianBlur(gray,(3,3),0)
plt.figure(figsize=(13,13))
plt.subplot(1,2,1)
plt.imshow(img_c)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gray)
plt.title("Gray Image")
plt.axis("off")
plt.show()

```
## Output
![image](https://github.com/vasanth0908/Edge-Linking-using-Hough-Transformm/assets/122000018/1463a0e1-02b2-4d3a-abb1-6a6b5271b982)


### Canny Edge detector output
```
canny=cv2.Canny(gray,120,150)
plt.imshow(canny)
plt.title("Canny Edge Detector")
plt.axis("off")
plt.show()

```
## Output
![image](https://github.com/vasanth0908/Edge-Linking-using-Hough-Transformm/assets/122000018/8020ab54-7c25-474d-946f-03d9e29cae62)


### Display the result of Hough transform
```
lines=cv2.HoughLinesP(canny,1,np.pi/180,threshold=80,minLineLength=50,maxLineGap=250)
for line in lines:
    x1,y1,x2,y2=line[0]
    cv2.line(img_c,(x1,y1),(x2,y2),(255,0,0),3)
plt.imshow(img_c)
plt.title("Result Image")
plt.axis("off")
plt.show()

```
## Output
![image](https://github.com/vasanth0908/Edge-Linking-using-Hough-Transformm/assets/122000018/80a6c8cb-74be-43f4-9eda-da4443f33563)

## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform.
