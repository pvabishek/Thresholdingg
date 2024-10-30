# THRESHOLDING->
## Aim:
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required:
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm:
### Step 1:
Load the necessary packages.

### Step 2:
Read the Image and convert to grayscale

### Step 3:
Use Global thresholding to segment the image.

### Step 4:
Use Adaptive thresholding to segment the image.

### Step 5:
Use Otsu's method to segment the image and display the results.

## Program:
```
Developed By:ABISHEK PV
Reg No: 212222230003
```
### Original Image
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the image
image = cv2.imread('mikey1.jpg')
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.xticks([]), plt.yticks([])
plt.show()

```
### Output
![download](https://github.com/user-attachments/assets/6ff2f371-907d-44ae-bf2c-6e3a87e85fea)


### Global Thresholding
```
# Global thresholding
ret_global, th_global = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)

plt.imshow(th_global, cmap='gray')
plt.title('Global Thresholding (v=127)')
plt.xticks([]), plt.yticks([])
plt.show()
```
### Output
![download](https://github.com/user-attachments/assets/6cd6559b-dd4b-45b9-9e60-490a50e315a8)

### Adaptive Thresholding
```
# Adaptive thresholding (Gaussian)
th_adaptive = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY, 11, 2)

plt.imshow(th_adaptive, cmap='gray')
plt.title('Adaptive Gaussian Thresholding')
plt.xticks([]), plt.yticks([])
plt.show()
```
### Output
![download](https://github.com/user-attachments/assets/8db3a434-db44-476c-8f86-12f92727a8d1)

### Optimum Global Thesholding using Otsu's Method
```
# Otsu's thresholding
ret_otsu, th_otsu = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)

plt.imshow(th_otsu, cmap='gray')
plt.title("Otsu's Thresholding")
plt.xticks([]), plt.yticks([])
plt.show()
```
### Output
![download](https://github.com/user-attachments/assets/43493e03-1169-47cb-bc98-1efd64c28ae6)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
