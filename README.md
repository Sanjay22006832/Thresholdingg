# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the input image using cv2.imread() and convert it to a grayscale image using cv2.cvtColor() with the color conversion code cv2.COLOR_BGR2GRAY.

### Step2:
Use a fixed threshold value (e.g., 127) for global thresholding with cv2.threshold(). Pixels with intensity above this value are set to maximum intensity (255), and the rest are set to minimum intensity (0).

### Step3:
Use adaptive thresholding, which calculates the threshold for smaller regions of the image. The threshold is calculated dynamically using cv2.adaptiveThreshold() with the ADAPTIVE_THRESH_GAUSSIAN_C method.

### Step4:
Otsu's method automatically finds an optimal threshold value by minimizing the within-class variance. Apply it using cv2.threshold() with the flag cv2.THRESH_OTSU.

### Step5:
Use plt.imshow() to visualize the grayscale image and the segmented images from global, adaptive, and Otsu's thresholding techniques.

## Program
### NAME: M Sanjay
### REG NO. 212222240090


# Load the necessary packages
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

# Read the Image and convert to grayscale
```
# Read the image
image = cv2.imread('death note.jpg')

# Convert to grayscale
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Display the original grayscale image
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.xticks([]), plt.yticks([])
plt.show()
```
### OUTPUT:

![Screenshot 2024-10-17 145131](https://github.com/user-attachments/assets/6d03b8f7-c0e5-4dbb-a0c7-65743319e777)

# Use Global thresholding to segment the image
```
# Global thresholding
ret_global, th_global = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)

# Display the global thresholding result
plt.imshow(th_global, cmap='gray')
plt.title('Global Thresholding (v=127)')
plt.xticks([]), plt.yticks([])
plt.show()
```
### OUTPUT:
![Screenshot 2024-10-17 145136](https://github.com/user-attachments/assets/88104a0d-25e0-4b37-8e6f-363aa8be7331)

# Use Adaptive thresholding to segment the image
```
# Adaptive thresholding (Gaussian)
th_adaptive = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C,
                                    cv2.THRESH_BINARY, 11, 2)

# Display the adaptive thresholding result
plt.imshow(th_adaptive, cmap='gray')
plt.title('Adaptive Gaussian Thresholding')
plt.xticks([]), plt.yticks([])
plt.show()
```
### OUTPUT:
![Screenshot 2024-10-17 145142](https://github.com/user-attachments/assets/ed248c5c-0a09-4122-ae14-24f8dcf88dbf)

# Use Otsu's method to segment the image 
```
# Otsu's thresholding
ret_otsu, th_otsu = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)

# Display the Otsu thresholding result
plt.imshow(th_otsu, cmap='gray')
plt.title("Otsu's Thresholding")
plt.xticks([]), plt.yticks([])
plt.show()
```
### OUTPUT:
![Screenshot 2024-10-17 145148](https://github.com/user-attachments/assets/5abaaf22-a546-469f-8052-ecdb2ffe5167)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
