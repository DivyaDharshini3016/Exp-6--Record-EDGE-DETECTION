# Exp-6--Record-EDGE-DETECTION
## Aim
To perform edge detection using Sobel, Roberts, Prewitt, Laplacian, and Canny edge detectors.

## Software Required

Anaconda – Python 3.7

Jupyter Notebook / VS Code

OpenCV (cv2)

NumPy

Matplotlib

## ⚙️ Algorithm
### Step 1:
Import all the necessary modules for the program.

### Step 2:
Load an image using cv2.imread().

### Step 3:
Convert the image to grayscale.

### Step 4:
Apply Sobel operator using OpenCV to detect edges.

### Step 5:
Apply Prewitt operator using custom kernels.

### Step 6:
Apply Roberts operator using custom kernels.

### Step 7:
Apply Laplacian operator using OpenCV.

### Step 8:
Apply Canny edge detector using OpenCV.

### Step 9:
Display all edge-detected images for comparison.

## Program:

Developed By
Name: Divya Dharshini S
Register No: 212224240039
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('photo1.jpg')  # Replace with your image path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
# Original Image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')
sobel_x = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=5)  # Sobel in x direction
sobel_y = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=5)  # Sobel in y direction
sobel_combined = cv2.magnitude(sobel_x, sobel_y)  # Combine both directions
plt.imshow(sobel_combined, cmap='gray')
plt.title('Sobel Edge Detection')
plt.axis('off')
laplacian = cv2.Laplacian(gray_image, cv2.CV_64F)
plt.imshow(laplacian, cmap='gray')
plt.title('Laplacian Edge Detection')
plt.axis('off')
canny_edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off')
```

## Output

### Original Image

<img width="728" height="547" alt="image" src="https://github.com/user-attachments/assets/2ad5d139-2d8b-4839-a823-fec06e9b499e" />

### Sobel Edge Detector

<img width="731" height="555" alt="image" src="https://github.com/user-attachments/assets/da7837d2-93fa-480b-bada-028b0df0a6f9" />

### Laplacian Edge Detector

<img width="742" height="547" alt="image" src="https://github.com/user-attachments/assets/26ed9f5b-f718-4f42-91e1-6860c2f35342" />


### Canny Edge Detector

<img width="767" height="537" alt="image" src="https://github.com/user-attachments/assets/522cf6e0-2b5b-4f51-b43a-5e6d055c10b5" />


## Result
Thus, edges are successfully detected using Sobel, Prewitt, Roberts, Laplacian, and Canny edge detection techniques. Each method highlights edges differently based on gradient and intensity variations, improving feature extraction and analysis.
