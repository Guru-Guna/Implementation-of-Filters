# Implementation-of-Filters
## Aim:

To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step 1:
Import the required libraries and read the image.

### Step 2:
Convert the saved BGR image to RGB using cvtColor().

### Step 3:
Use the filters required for image smoothing and sharpening.

### Step 4:
Apply the filters using cv2.filter2D() for each respective filters.
 

### Step 5:
Plot the images of the original one and the filtered one using plt.figure() and cv2.imshow().
 

## Program:
~~~
Developed By   : Gunaseelan G
Register Number: 212221230031
~~~
~~~
import cv2
import numpy as np
import matplotlib.pyplot as plt
image=cv2.imread('bike.png')
image2=cv2.cvtColor (image1, cv2.COLOR_BGR2RGB)
~~~
## 1. Smoothing Filters :
### i) Using Averaging Filter:
~~~
kernel1 = np.ones((11,11),np.float32)/121
avg_filter = cv2.filter2D(image2,-1,kernel1)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(avg_filter)
plt.title("Filtered")
plt.axis("off")
~~~
### ii) Using Weighted Averaging Filter:
~~~
kernel2 = np.array([[1,2,1],[2,4,2],[1,2,1]])/16
weighted_filter = cv2.filter2D(image2,-1,kernel2)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(weighted_filter)
plt.title("Filtered")
plt.axis("off")
~~~
### iii) Using Gaussian Filter:
~~~
gaussian_blur = cv2.GaussianBlur(src = image2, ksize = (11,11), sigmaX=0, sigmaY=0)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Filtered")
plt.axis("off")
~~~
### iv) Using Median Filter:
~~~
median = cv2.medianBlur(src=image2,ksize = 11)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Filtered (Median)")
plt.axis("off")
~~~
## 2. Sharpening Filters:
### i) Using Laplacian Kernal:
~~~
kernel3 = np.array([[0,1,0],[1,-4,1],[0,1,0]])
laplacian_kernel = cv2.filter2D(image2,-1,kernel3)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian_kernel)
plt.title("Filtered (Laplacian Kernel)")
plt.axis("off")
~~~
### ii) Using Laplacian Operator:

~~~
laplacian_operator = cv2.Laplacian(image2,cv2.CV_64F)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian_operator)
plt.title("Filtered (Laplacian Operator)")
plt.axis("off")
~~~

## Output:
### Smoothing Filters:
#### i)  Using Averaging Filter:

![img1](https://user-images.githubusercontent.com/93427255/230881888-0dceda36-0c32-4dbc-9ed6-5c9b22207145.png)


#### ii) Using Weighted Average Filter:

![img2](https://user-images.githubusercontent.com/93427255/230881923-39b4bc71-e791-406c-aa2f-2fd86b8123f6.png)


#### iii) Using Gaussian Filter:

![img3](https://user-images.githubusercontent.com/93427255/230881949-be6caef2-d3a2-4a1e-aeb8-8556e10e4bc1.png)


#### iv) Using Median Filter:

![img4](https://user-images.githubusercontent.com/93427255/230881975-19385751-21cd-43b7-b4c7-198167af4292.png)


### Sharpening Filters:

#### i) Using Laplacian Kernel:

![img5](https://user-images.githubusercontent.com/93427255/230881995-02020534-78aa-474d-b4e4-ea3114e1557f.png)


#### ii) Using Laplacian Operator:


![img6](https://user-images.githubusercontent.com/93427255/230882109-157698ea-bfdd-46be-ae78-841a0fe862c1.png)


## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
