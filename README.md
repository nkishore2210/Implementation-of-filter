## EX-5  Implementation-of-filter

## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step 1:
Import necessary libraries: OpenCV, NumPy, and Matplotlib.Read an image, convert it to RGB format, define an 11x11 averaging kernel, and apply 2D convolution filtering.Display the original and filtered images side by side using Matplotlib.
<br>
### Step 2:
Define a weighted averaging kernel (kernel2) and apply 2D convolution filtering to the RGB image (image2).Display the resulting filtered image (image4) titled 'Weighted Averaging Filtered' using Matplotlib's imshow function.
<br>
### Step 3:
Apply Gaussian blur with a kernel size of 11x11 and standard deviation of 0 to the RGB image (image2).Display the resulting Gaussian-blurred image (gaussian_blur) titled 'Gaussian Blurring Filtered' using Matplotlib's imshow function.
<br>
### Step 4:
Apply median blur with a kernel size of 11x11 to the RGB image (image2).Display the resulting median-blurred image (median) titled 'Median Blurring Filtered' using Matplotlib's imshow function.
<br>
### Step 5 :
Define a Laplacian kernel (kernel3) and perform 2D convolution filtering on the RGB image (image2).Display the resulting filtered image (image5) titled 'Laplacian Kernel' using Matplotlib's imshow function.
<br>
### Step 6 :
Apply the Laplacian operator to the RGB image (image2) using OpenCV's cv2.Laplacian function.Display the resulting image (new_image) titled 'Laplacian Operator' using Matplotlib's imshow function.
<br>

## Program:
### Developed By   : KISHORE
### Register Number: 212222240049
</br>

```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('ryan gosling.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)
plt.figure(figsize=(9,9))
plt.imshow(image2)
plt.title('Original')
plt.axis('off')
```

### 1. Smoothing Filters

i) Using Averaging Filter
```Python
kernel = np.ones((11,11), np. float32)/121
image3 = cv2.filter2D(image2, -1, kernel)

plt.imshow(image3)
plt.title('Filtered')
plt.axis('off')
```
ii) Using Weighted Averaging Filter
```Python
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

kernel2 = np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image4 = cv2.filter2D(image2, -1, kernel2)
plt.imshow(image4)
plt.title('Weighted Averaging Filtered')
```
iii) Using Gaussian Filter
```Python
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

gaussian_blur = cv2.GaussianBlur(src=image2, ksize=(11,11), sigmaX=0, sigmaY=0)
plt.imshow(gaussian_blur)
plt.title(' Gaussian Blurring Filtered')
```

iv) Using Median Filter
```Python
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

median=cv2.medianBlur (src=image2, ksize=11)
plt.imshow(median)
plt.title(' Median Blurring Filtered')
```

### 2. Sharpening Filters
i) Using Laplacian Kernal
```Python
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

kernel3 = np.array([[0,1,0], [1, -4,1],[0,1,0]])
image5 =cv2.filter2D(image2, -1, kernel3)
plt.imshow(image5)
plt.title('Laplacian Kernel')
```
ii) Using Laplacian Operator
```Python
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

new_image = cv2.Laplacian (image2, cv2.CV_64F)
plt.imshow(new_image)
plt.title('Laplacian Operator')
```

## OUTPUT:

### ORIGINAL IMAGE:
![Screenshot 2024-10-14 095801](https://github.com/user-attachments/assets/6c1d0b99-acbd-44f5-88e1-b3cc0bec2c49)

### 1. Smoothing Filters

i) Using Averaging Filter
![Screenshot 2024-10-14 095640](https://github.com/user-attachments/assets/dbca54ed-caf6-46ad-8c42-98865a549326)

ii)Using Weighted Averaging Filter
![Screenshot 2024-10-14 095647](https://github.com/user-attachments/assets/ff58357f-6655-4951-929b-bc5893e541bf)

iii)Using Gaussian Filter
![Screenshot 2024-10-14 095654](https://github.com/user-attachments/assets/afd10eb8-e93f-4d4b-bf6e-1ded096d9010)

iv) Using Median Filter
![Screenshot 2024-10-14 095700](https://github.com/user-attachments/assets/eba7ad17-063e-46b1-a42f-d7564b85ef5d)

### 2. Sharpening Filters

i) Using Laplacian Kernal
![Screenshot 2024-10-14 095706](https://github.com/user-attachments/assets/32ee5551-da62-4ba3-b228-02729e61f006)

ii) Using Laplacian Operator
![Screenshot 2024-10-14 095712](https://github.com/user-attachments/assets/a53f09db-18af-4b66-b9d6-cf80ab7ff716)

## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
