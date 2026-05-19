# EX 4
# IMAGE-TRANSFORMATIONS

## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import necessary libraries such as OpenCV, NumPy, and Matplotlib for image processing and visualization.

### Step2:
Read the input image using cv2.imread() and store it in a variable for further processing.

### Step3:
Apply various transformations like translation, scaling, shearing, reflection, rotation, and cropping by defining corresponding functions:

1.Translation moves the image along the x or y-axis.

2.Scaling resizes the image by scaling factors.

3.Shearing distorts the image along one axis.

4.Reflection flips the image horizontally or vertically.

5.Rotation rotates the image by a given angle.

### Step4:
Display the transformed images using Matplotlib for visualization. Convert the BGR image to RGB format to ensure proper color representation.

### Step5:
Save or display the final transformed images for analysis and use plt.show() to display them inline in Jupyter or compatible environments.

## Program:
```python
Developed By :Nikshitha S
Register Number:212224040220
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Load the image
image = cv2.imread('flower.jpg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)  # Convert BGR to RGB for Matplotlib

# 1. Translation
rows, cols, _ = image.shape
M_translate = np.float32([[1, 0, 50], [0, 1, 100]])  # Translate by (50, 100) pixels
translated_image = cv2.warpAffine(image_rgb, M_translate, (cols, rows))

# 2. Scaling
scaled_image = cv2.resize(image_rgb, None, fx=1.5, fy=1.5, interpolation=cv2.INTER_LINEAR)  # Scale by 1.5x

# 3. Shearing
M_shear = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  # Shear with factor 0.5
sheared_image = cv2.warpAffine(image_rgb, M_shear, (int(cols * 1.5), int(rows * 1.5)))

# 4. Reflection (Flip)
reflected_image = cv2.flip(image_rgb, 1)  # Horizontal reflection (flip along y-axis)

# 5. Rotation
M_rotate = cv2.getRotationMatrix2D((cols / 2, rows / 2), 45, 1)  # Rotate by 45 degrees
rotated_image = cv2.warpAffine(image_rgb, M_rotate, (cols, rows))

# 6.Cropping
cropped_image = image_rgb[50:300, 100:400]  # Crop a portion of the image

# Plot the original and transformed images
plt.figure(figsize=(12, 8))
```
```
plt.imshow(image_rgb)
plt.title("Original Image")
plt.axis('off')
```
# Output:

<img width="184" height="298" alt="image" src="https://github.com/user-attachments/assets/99537d55-d295-4167-9ce4-cdfe6b05d645" />


# 1. Translation
```
plt.imshow(translated_image)
plt.title("Translated Image")
plt.axis('off')
```
### Output:

<img width="381" height="257" alt="image" src="https://github.com/user-attachments/assets/acd6305e-225e-438a-b07e-f39f66b021ad" />


# 2. Scaling
```
plt.imshow(scaled_image)
plt.title("Scaled Image")
plt.axis('off')
```
### Output:

<img width="353" height="272" alt="image" src="https://github.com/user-attachments/assets/d3f69898-2b81-479b-b686-1d5966a77244" />


# 3. Shearing
```
plt.imshow(sheared_image)
plt.title("Sheared Image")
plt.axis('off')
```
### Output:

<img width="159" height="284" alt="image" src="https://github.com/user-attachments/assets/2be48829-694d-4cad-be55-451428efbd16" />


# 4. Reflection (Flip)
```
plt.imshow(reflected_image)
plt.title("Reflected Image")
plt.axis('off')
```
### Output:


<img width="159" height="283" alt="image" src="https://github.com/user-attachments/assets/3faa1e61-08a8-488c-96df-7430b24eb67c" />


# 5. Rotation
```
plt.imshow(rotated_image)
plt.title("Rotated Image")
plt.axis('off')
```
### Output:

<img width="156" height="285" alt="image" src="https://github.com/user-attachments/assets/8e34a807-0e23-4057-bea8-9a2af42130a2" />



# 6.Cropping
```
plt.tight_layout()
plt.show()

# Plot cropped image separately as its aspect ratio may be different
plt.figure(figsize=(4, 4))
plt.imshow(cropped_image)
plt.title("Cropped Image")
plt.axis('off')
plt.show()
```
### Output:

<img width="358" height="290" alt="image" src="https://github.com/user-attachments/assets/e772d88d-c561-4718-b991-4c1c33096a1c" />



## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
