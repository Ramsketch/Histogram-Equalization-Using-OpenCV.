# Histogram-of-an-images

# **Name:** RAMKUMAR S

# **Register Number:** 212225240115


## Aim

To obtain a histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255. Also, write a Python program using OpenCV to perform histogram equalization.

## Software Required

- Anaconda - Python 3.7
- OpenCV
- NumPy
- Matplotlib

## Algorithm

### Step 1
Read the grayscale and color images using the `cv2.imread()` function.

### Step 2
Display the grayscale and color images using the `imshow()` function.

### Step 3
Use the `cv2.calcHist()` function to calculate the frequency of pixel intensities in the grayscale image.

### Step 4
Use the `cv2.calcHist()` function to calculate the histograms of the Blue, Green, and Red channels of the color image.

### Step 5
Plot and display the histograms of the grayscale image and color image.

## Program

**Developed By:** RAMKUMAR S

**Register Number:** 212225240115

python
```

import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read Grayscale Image
img = cv2.imread('parrot.webp', cv2.IMREAD_GRAYSCALE)

# Display Original Grayscale Image
plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()

# Original Histogram
plt.hist(img.ravel(), 256, range=[0, 256])
plt.title('Original Histogram')
plt.show()

# Histogram Equalization
img_eq = cv2.equalizeHist(img)

# Equalized Histogram
plt.hist(img_eq.ravel(), 256, range=[0, 256])
plt.title('Equalized Histogram')
plt.show()

# Display Equalized Image
plt.imshow(img_eq, cmap='gray')
plt.title('Equalized Image')
plt.show()

# Read Color Image
img = cv2.imread('parrot.webp', cv2.IMREAD_COLOR)

# Convert BGR to HSV
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)

# Apply Histogram Equalization to V Channel
img_hsv[:, :, 2] = cv2.equalizeHist(img_hsv[:, :, 2])

# Convert HSV to BGR
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)

# Display Equalized Color Image
plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Color Image')
plt.show()

# Histogram of Equalized Color Image
plt.hist(img_eq.ravel(), 256, range=[0, 256])
plt.title('Histogram Equalized')
plt.show()

# Compare Original and Equalized Color Images
plt.figure(figsize=(20, 10))

plt.subplot(221)
plt.imshow(img[:, :, ::-1])
plt.title('Original Color Image')

plt.subplot(222)
plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Color Image')

plt.show()

# Compare Original and Equalized Histograms
plt.figure(figsize=(15, 4))

plt.subplot(121)
plt.hist(img.ravel(), 256, range=[0, 256])
plt.title('Original Image Histogram')

plt.subplot(122)
plt.hist(img_eq.ravel(), 256, range=[0, 256])
plt.title('Equalized Image Histogram')

plt.show()


```



## Output

### Input Grayscale Image

<img width="413" height="251" alt="image" src="https://github.com/user-attachments/assets/680ae0a1-8f3a-485d-872f-6f840b63ebf9" />


### Input Grayscale Image Range

<img width="421" height="250" alt="image" src="https://github.com/user-attachments/assets/163e0dc6-0dec-41eb-9993-b6e71ea53218" />


### Input Grayscale Image Equalized Histogram

<img width="422" height="255" alt="image" src="https://github.com/user-attachments/assets/bc83a2b5-ca22-4c02-8309-4ff348326b76" />



### Histogram of Grayscale Image and Color Image Channels

### Original Image

<img width="413" height="251" alt="image" src="https://github.com/user-attachments/assets/680ae0a1-8f3a-485d-872f-6f840b63ebf9" />


### Equalized Image

<img width="410" height="257" alt="image" src="https://github.com/user-attachments/assets/cd7d1f7d-f093-4ac1-81ca-54b16c668bf6" />


### Equalized Histogram

<img width="424" height="255" alt="image" src="https://github.com/user-attachments/assets/5b50da23-2e4a-42f4-8f43-8c82b912560f" />


### Final Output of Original Image and Equalized 

<img width="728" height="232" alt="image" src="https://github.com/user-attachments/assets/9ef610e5-4c76-4ee3-8636-5dab5cb75a14" />


### Final Output of Original Image and its Histogram Equalized

<img width="722" height="220" alt="image" src="https://github.com/user-attachments/assets/e8a7be38-2007-443f-acd9-228b6bbe6d0a" />


## Result

Thus, the histogram showing the frequency of pixel intensities ranging from 0 to 255 was obtained for the grayscale image and the color image using OpenCV.
