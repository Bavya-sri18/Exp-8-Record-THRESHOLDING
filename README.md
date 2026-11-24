# Exp-8-Record-THRESHOLDING

## NAME : BAVYA SRI B
## REGISTER NUMBER : 212224230034

## Aim

To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Used

Anaconda – Python 3.7

Jupyter Notebook / VS Code

OpenCV (cv2)

NumPy

Matplotlib

## Algorithm

#### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

#### Step 2:
Load the input image using OpenCV.

#### Step 3:
Convert the input image into grayscale format.

#### Step 4: Global Thresholding
Select a fixed threshold value.

Apply thresholding to separate foreground and background pixels.

Display the thresholded image.

#### Step 5: Adaptive Thresholding
Compute threshold values for small regions of the image.

Apply Adaptive Mean Thresholding.

Apply Adaptive Gaussian Thresholding.

Display the segmented images.

#### Step 6: Otsu's Thresholding
Automatically determine the optimal threshold value.

Apply Otsu's thresholding technique.

Display the segmented image.

#### Step 7:
Compare the results obtained from Global, Adaptive, and Otsu's thresholding methods.


## Program

```PYTHON
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread(r"D:\Screenshots\Bavya.jpeg")  
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  
plt.title("Original Image")
plt.axis('off')

_, global_thresholded = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)

adaptive_thresholded = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)

_, otsu_thresholded = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)

# Global Thresholding
plt.subplot(2, 2, 2)
plt.imshow(global_thresholded, cmap='gray')
plt.title("Global Thresholding")
plt.axis('off')

# Adaptive Thresholding
plt.subplot(2, 2, 3)
plt.imshow(adaptive_thresholded, cmap='gray')
plt.title("Adaptive Thresholding")
plt.axis('off')

# Otsu's Method
plt.subplot(2, 2, 4)
plt.imshow(otsu_thresholded, cmap='gray')
plt.title("Otsu's Method")
plt.axis('off')

# Show the plot
plt.tight_layout()
plt.show()

```

## Output

## Original Image

<img width="875" height="352" alt="image" src="https://github.com/user-attachments/assets/588b5c70-0a3a-4c0b-9e9b-61e29c656985" />

## Global Thresholding

<img width="281" height="367" alt="image" src="https://github.com/user-attachments/assets/7b49d42d-b5be-43b2-a2e3-24f83535a0ef" />

## Adaptive Thresholding

<img width="327" height="380" alt="image" src="https://github.com/user-attachments/assets/b3f6f2f1-c25d-41bd-8170-92af1640c414" />

## Otsu's Thresholding

<img width="270" height="372" alt="image" src="https://github.com/user-attachments/assets/94fcc458-e59c-4339-8ccd-13a48019d21c" />


## Result
Thus, image segmentation is successfully performed using Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding techniques in OpenCV.
