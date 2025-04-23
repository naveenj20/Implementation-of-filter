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
### Developed By   : Naveen Jaisanker 
### Register Number: 212224110039

### 1. Smoothing Filters

i) Using Averaging Filter

```python
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("bridge.jpeg")
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

```python
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

```python
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

```python
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

i) Using Laplacian Linear Kernel

```python
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

```python
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

![Screenshot 2025-04-23 210800](https://github.com/user-attachments/assets/5ab294c1-9d29-4cd2-b78a-af2fa06f6560)

ii)Using Weighted Averaging Filter

![Screenshot 2025-04-23 210827](https://github.com/user-attachments/assets/8850bd2b-3bbe-49da-a47e-47b0e3008df4)

iii)Using Gaussian Filter

![Screenshot 2025-04-23 210847](https://github.com/user-attachments/assets/601b9bb3-abc4-40be-a7ba-2017230b7bdb)

iv) Using Median Filter

![Screenshot 2025-04-23 210911](https://github.com/user-attachments/assets/82ef2ded-3593-41e8-ac71-facbd0c9a2ce)

### 2. Sharpening Filters

i) Using Laplacian Kernal

![Screenshot 2025-04-23 210929](https://github.com/user-attachments/assets/da511822-f6f1-48b0-8233-db41978fe934)

ii) Using Laplacian Operator

![Screenshot 2025-04-23 210948](https://github.com/user-attachments/assets/50c54418-f7f8-4ac3-9b7a-ac54bac0aaa3)

## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
