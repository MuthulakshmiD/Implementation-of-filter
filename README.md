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
End the program

## Program:
### Developed By   : Muthulakshmi D
### Register Number: 212223040122


### 1. Smoothing Filters

i) Using Averaging Filter
```
import cv2
import numpy as np
import matplotlib.pyplot as 
image = cv2.imread('pcb.webp', cv2.IMREAD_GRAYSCALE)
kernel = np.ones((4, 4), np.float32) / 9
averaged_image = cv2.filter2D(image, -1, kernel)
plt.imshow(averaged_image, cmap='gray')
plt.title("Averaging Filter")
plt.axis('off')
plt.show()



```
ii) Using Weighted Averaging Filter
```Python
weighted_kernel = np.array([[1, 2, 1], 
                            [2, 4, 2], 
                            [1, 2, 1]], np.float32)

weighted_kernel = weighted_kernel / weighted_kernel.sum() 
weighted_image = cv2.filter2D(image, -1, weighted_kernel)  

plt.imshow(weighted_image, cmap='gray')
plt.title("Weighted Averaging Filter")
plt.axis('off')
plt.show()

```
iii) Using Gaussian Filter
```Python

gaussian_image = cv2.GaussianBlur(image, (3, 3), 1)
plt.imshow(gaussian_image, cmap='gray')
plt.title("Gaussian Filter")
plt.axis('off')
plt.show()


```
iv)Using Median Filter
```Python

median_image = cv2.medianBlur(image, 3)
plt.imshow(median_image, cmap='gray')
plt.title("Median Filter")
plt.axis('off')
plt.show()


```

### 2. Sharpening Filters
i) Using Laplacian Linear Kernal
```Python

laplacian_kernel = np.array([[0, 1, 0], [1, -4, 1], [0, 1, 0]], np.float32)
laplacian_image = cv2.filter2D(image, -1, laplacian_kernel)

sharpened_laplacian_image = cv2.add(image, laplacian_image)
plt.imshow(sharpened_laplacian_image, cmap='gray')
plt.title("Laplacian Kernel")
plt.axis('off')
plt.show()
```
ii) Using Laplacian Operator
```Python

laplacian_operator_image = cv2.Laplacian(image, cv2.CV_64F)  # Laplacian operator
laplacian_operator_image = cv2.convertScaleAbs(laplacian_operator_image)  # Convert to absolute values
sharpened_operator_image = cv2.add(image, laplacian_operator_image)

plt.imshow(sharpened_operator_image, cmap='gray')
plt.title("Laplacian Operator")
plt.axis('off')
plt.show()

```

## OUTPUT:
### 1. Smoothing Filters

i) Using Averaging Filter

<img width="703" height="465" alt="image" src="https://github.com/user-attachments/assets/2c0caedb-0c09-48a8-b64e-bed4d3110e50" />

ii)Using Weighted Averaging Filter

<img width="714" height="479" alt="image" src="https://github.com/user-attachments/assets/f596bf76-d984-4111-8248-009459158f88" />

iii)Using Gaussian Filter

<img width="691" height="468" alt="image" src="https://github.com/user-attachments/assets/b3472065-5751-4e27-9249-5a7a32024731" />

iv) Using Median Filter

<img width="706" height="482" alt="image" src="https://github.com/user-attachments/assets/1ccd3710-1db0-4294-9946-e1e8d69a33ab" />



### 2. Sharpening Filters
</br>

i) Using Laplacian Kernal

<img width="740" height="464" alt="image" src="https://github.com/user-attachments/assets/159946f3-d56e-4284-bab5-fe198bcce008" />



ii) Using Laplacian Operator

<img width="723" height="475" alt="image" src="https://github.com/user-attachments/assets/b7ac0234-b212-4ffe-a3c0-fb3639fbb9cc" />



## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
