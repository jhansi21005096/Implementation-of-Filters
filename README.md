# Implementation-of-Filters
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
 Import cv2, matplotlib.py libraries and read the saved images using cv2.imread().



### Step2
Convert the saved BGR image to RGB using cvtColor().

### Step3
 By using the following filters for image smoothing:filter2D(src, ddepth, kernel), Box filter,Weighted Average filter,GaussianBlur(src, ksize, sigmaX[, dst[, sigmaY[, borderType]]]), medianBlur(src, ksize),and for image sharpening:Laplacian Kernel,Laplacian Operator.

### Step4
Apply the filters using cv2.filter2D() for each respective filters.

### Step5
Plot the images of the original one and the filtered one using plt.figure() and cv2.imshow().

## Program:
### Developed By   :K.Jhansi
### Register Number:212221230045
</br>

### 1. Smoothing Filters

i) Using Averaging Filter

import cv2

import numpy as np

import matplotlib.pyplot as plt

image = cv2.imread('simage.jpg')

image1 = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)

kernel = np.ones((11,11),np.float32)/121

image2 = cv2.filter2D(image1,-1,kernel)

plt.figure(figsize =(15,15))

plt.subplot(1,2,1)

plt.imshow(image1)

plt.title('Original')

plt.axis('off')

plt.subplot(1,2,2)

plt.imshow(image2)

plt.title('Box Filter')

plt.axis('off')


ii) Using Weighted Averaging Filter

kernel1 = np.array([[1,2,1],[2,4,2],[1,2,1]])/30

image2 = cv2.filter2D(image1,-1,kernel1)

plt.figure(figsize =(15,15))

plt.subplot(1,2,1)

plt.imshow(image1)

plt.title('Original')

plt.axis('off')

plt.subplot(1,2,2)

plt.imshow(image2)

plt.title('Weighted Averaging Filter')

plt.axis('off')


iii) Using Gaussian Filter

gaussian_blur = cv2.GaussianBlur(src = image1, ksize = (11,11), sigmaX=0, sigmaY=0)

plt.figure(figsize = (15,15))

plt.subplot(1,2,1)

plt.imshow(image1)

plt.title("Original")

plt.axis("off")

plt.subplot(1,2,2)

plt.imshow(gaussian_blur)

plt.title("Gaussian Filter")

plt.axis("off")



iv) Using Median Filter

median = cv2.medianBlur(src = image1,ksize = 11)

plt.figure(figsize = (15,15))

plt.subplot(1,2,1)

plt.imshow(image1)

plt.title("Original")

plt.axis("off")

plt.subplot(1,2,2)

plt.imshow(gaussian_blur)

plt.title("Median Filter")

plt.axis("off")



### 2. Sharpening Filters
i) Using Laplacian Kernal

kernel3 = np.array([[0,1,0],[1,-4,1],[0,1,0]])

laplacian_kernel = cv2.filter2D(image1,-1,kernel3)

plt.figure(figsize = (15,15))

plt.subplot(1,2,1)

plt.imshow(image1)

plt.title("Original")

plt.axis("off")

plt.subplot(1,2,2)

plt.imshow(laplacian_kernel)

plt.title("laplacian kernel")

plt.axis("off")




ii) Using Laplacian Operator

laplacian_operator = cv2.Laplacian(image1,cv2.CV_64F)

plt.figure(figsize = (15,15))

plt.subplot(1,2,1)

plt.imshow(image1)

plt.title("Original")

plt.axis("off")

plt.subplot(1,2,2)

plt.imshow(laplacian_operator)

plt.title("laplacian operator")

plt.axis("off")



## OUTPUT:
### 1. Smoothing Filters

i) Using Averaging Filter
![output](https://github.com/jhansi21005096/Implementation-of-Filters/blob/main/dpoutput1.png)

ii) Using Weighted Averaging Filter
![output](https://github.com/jhansi21005096/Implementation-of-Filters/blob/main/dpoutput2.png)

iii) Using Gaussian Filter
![output](https://github.com/jhansi21005096/Implementation-of-Filters/blob/main/dpoutput3.png)

iv) Using Median Filter
![output](https://github.com/jhansi21005096/Implementation-of-Filters/blob/main/dpoutput4.png)

### 2. Sharpening Filters

i) Using Laplacian Kernal
![output](https://github.com/jhansi21005096/Implementation-of-Filters/blob/main/dpoutput5.png)

ii) Using Laplacian Operator
![output](https://github.com/jhansi21005096/Implementation-of-Filters/blob/main/dpoutput6.png)

## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
