# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm
### Step1:
Load the necessary packages.
### Step2:
Read the Image and convert to grayscale.
### Step3:
Use Global thresholding to segment the image.
### Step4:
Use Adaptive thresholding to segment the image.
### Step5:
Use Otsu's method to segment the image and display the results.

## Program
### Developed By : SHABREENA VINCENT
### Register Number : 212222230141
```python
# Load the necessary packages

import numpy as np
import matplotlib.pyplot as plt
import cv2
# Read the Image and convert to grayscale

image = cv2.imread('lap.jpeg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('lap.jpeg',0)

# Use Global thresholding to segment the image

ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)

# Use Adaptive thresholding to segment the image

thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

# Use Otsu's method to segment the image 

ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Display the results

titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
for i in range(0,9):
    plt.figure(figsize=(10,10))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()

```
## Output

### Original Image
![image](https://github.com/Safeeq-Fazil/Thresholdingg/assets/118680361/a7ce5809-4e33-4f1f-9668-25494e16fbdf)

### Global Thresholding

![image](https://github.com/Safeeq-Fazil/Thresholdingg/assets/118680361/a2056753-2b22-44a7-bea2-0ce4f5820e57)
![image](https://github.com/Safeeq-Fazil/Thresholdingg/assets/118680361/7664e877-c626-47a1-89b4-2de1d23df026)
![image](https://github.com/Safeeq-Fazil/Thresholdingg/assets/118680361/7aa21864-cc95-4533-9205-daa0ac2cdfef)
![image](https://github.com/Safeeq-Fazil/Thresholdingg/assets/118680361/f958314a-c285-44fd-aed0-3392c524f83b)
![image](https://github.com/Safeeq-Fazil/Thresholdingg/assets/118680361/a8b770b3-ce07-458e-9f9e-b4e9a82c0484)


### Adaptive Thresholding
![image](https://github.com/Safeeq-Fazil/Thresholdingg/assets/118680361/785cdb4f-f29c-4f10-a13b-3ccde08c83bc)
![image](https://github.com/Safeeq-Fazil/Thresholdingg/assets/118680361/dfbda153-74ac-4d3a-a8f7-98d8573fa2d9)


### Optimum Global Thesholding using Otsu's Method
![image](https://github.com/Safeeq-Fazil/Thresholdingg/assets/118680361/6979a5c8-a547-419c-91f3-82d148994f94)



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
