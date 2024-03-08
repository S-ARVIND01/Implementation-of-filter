# Implementation-of-filter
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
Import the required libraries.

### Step2
Convert the image from BGR to RGB.

### Step3
Apply the required filters for the image separately.

### Step4
Plot the original and filtered image by using matplotlib.pyplot.

### Step5
End the program.

## Program:
```python
Developed By   : ARVIND S
Register Number: 212222240012
```

### 1. Smoothing Filters

i) Using Averaging Filter
```Python
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("scenery.jpg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
kernel=np.ones((11,11),np.float32)/169
image3=cv2.filter2D(image2,-1,kernel)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Average Filter Image")
plt.axis("off")
plt.show()
```
ii) Using Weighted Averaging Filter
```Python
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image3=cv2.filter2D(image2,-1,kernel1)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()
```
iii) Using Gaussian Filter
```Python
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()
```

iv) Using Median Filter
```Python
median=cv2.medianBlur(image2,13)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Median Blur")
plt.axis("off")
plt.show()
```

### 2. Sharpening Filters
i) Using Laplacian Kernal
```Python
kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()
```
ii) Using Laplacian Operator
```Python
laplacian=cv2.Laplacian(image2,cv2.CV_64F)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
```

## OUTPUT:
### 1. Smoothing Filters

i) Using Averaging Filter
![Screenshot 2024-03-08 203202](https://github.com/S-ARVIND01/Implementation-of-filter/assets/118707337/6d52b32d-63df-4d02-93e2-f5630168d3c1)

ii) Using Weighted Averaging Filter
![Screenshot 2024-03-08 203231](https://github.com/S-ARVIND01/Implementation-of-filter/assets/118707337/fa967394-682a-4220-813a-3d7e73c55548)

iii) Using Gaussian Filter
![Screenshot 2024-03-08 203257](https://github.com/S-ARVIND01/Implementation-of-filter/assets/118707337/becee9b3-458b-4f4f-a2be-b31f8c00088b)

iv) Using Median Filter
![Screenshot 2024-03-08 203316](https://github.com/S-ARVIND01/Implementation-of-filter/assets/118707337/720a8f30-3b9d-4248-a329-7191e00f83e2)

### 2. Sharpening Filters

i) Using Laplacian Kernal
![Screenshot 2024-03-08 203339](https://github.com/S-ARVIND01/Implementation-of-filter/assets/118707337/5e5e9e35-dd23-4c6b-918e-5f8c6a3755c0)

ii) Using Laplacian Operator
![Screenshot 2024-03-08 203359](https://github.com/S-ARVIND01/Implementation-of-filter/assets/118707337/f1a9abfa-a250-4cd2-8fd4-b56223c1aece)

## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
