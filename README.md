# Geometric Transformations Using OpenCV
### Developed By: NIKSHITHA S

### Register No: 212224040220
---

## Aim

To write a Python program using OpenCV to perform various geometric transformations on an image.

The program performs the following operations:

- Image Translation  
- Image Scaling  
- Image Shearing  
- Image Reflection  
- Image Rotation  
- Image Cropping  

---

## Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib  

---

## Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the input image in color mode.

### Step 3: Image Translation
- Create a translation matrix to shift the image  
- Move the image 100 pixels to the right and 50 pixels down  
- Apply transformation using `cv2.warpAffine()`  
- Display original and translated images  

### Step 4: Image Scaling
- Resize the image using scaling factors:
  - 5.0× in x direction  
  - 2.0× in y direction  
- Use `cv2.resize()`  
- Display original and scaled images  

### Step 5: Image Shearing
- Create shearing matrix  
- Apply shearing transformation using `cv2.warpAffine()`  
- Display original and sheared images  

### Step 6: Image Reflection
- Perform image reflection using `cv2.flip()`  
- Display reflected image  

### Step 7: Image Rotation
- Create rotation matrix for 45° rotation  
- Use `cv2.getRotationMatrix2D()` and `cv2.warpAffine()`  
- Display rotated image  

### Step 8: Image Cropping
- Define crop coordinates and dimensions  
- Extract selected image portion using array slicing  
- Display cropped image  

---

## Program

### Developed By: Kiruba RC

### Register No: 212224230125

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Step 1: Load the image
image = cv2.imread('Qn4.jpg')

# Display original image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Original Image")
plt.axis('off')

# Step 2: Image Translation
tx, ty = 100, 50
M_translation = np.float32([[1, 0, tx], [0, 1, ty]])
translated_image = cv2.warpAffine(image, M_translation, (image.shape[1], image.shape[0]))

plt.imshow(cv2.cvtColor(translated_image, cv2.COLOR_BGR2RGB))
plt.title("Translated Image")
plt.axis('off')

# Step 3: Image Scaling
fx, fy = 5.0, 2.0
scaled_image = cv2.resize(image, None, fx=fx, fy=fy, interpolation=cv2.INTER_LINEAR)

plt.imshow(cv2.cvtColor(scaled_image, cv2.COLOR_BGR2RGB))
plt.title("Scaled Image")
plt.axis('off')

# Step 4: Image Shearing
shear_matrix = np.float32([[1, 0.5, 0], [0.5, 1, 0]])
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))

plt.imshow(cv2.cvtColor(sheared_image, cv2.COLOR_BGR2RGB))
plt.title("Sheared Image")
plt.axis('off')

# Step 5: Image Reflection
reflected_image = cv2.flip(image, 2)

plt.imshow(cv2.cvtColor(reflected_image, cv2.COLOR_BGR2RGB))
plt.title("Reflected Image")
plt.axis('off')

# Step 6: Image Rotation
(height, width) = image.shape[:2]
angle = 45
center = (width // 2, height // 2)
M_rotation = cv2.getRotationMatrix2D(center, angle, 1)
rotated_image = cv2.warpAffine(image, M_rotation, (width, height))

plt.imshow(cv2.cvtColor(rotated_image, cv2.COLOR_BGR2RGB))
plt.title("Rotated Image")
plt.axis('off')

# Step 7: Image Cropping
x, y, w, h = 100, 100, 200, 150
cropped_image = image[y:y+h, x:x+w]

plt.imshow(cv2.cvtColor(cropped_image, cv2.COLOR_BGR2RGB))
plt.title("Cropped Image")
plt.axis('off')
```

---

## Output

### Image Translation

<img width="184" height="298" alt="image" src="https://github.com/user-attachments/assets/99537d55-d295-4167-9ce4-cdfe6b05d645" />


### Image Scaling
 
<img width="381" height="257" alt="image" src="https://github.com/user-attachments/assets/acd6305e-225e-438a-b07e-f39f66b021ad" />


### Image Shearing

<img width="353" height="272" alt="image" src="https://github.com/user-attachments/assets/d3f69898-2b81-479b-b686-1d5966a77244" />


### Image Reflection

  <img width="159" height="284" alt="image" src="https://github.com/user-attachments/assets/2be48829-694d-4cad-be55-451428efbd16" />


### Image Rotation

<img width="159" height="283" alt="image" src="https://github.com/user-attachments/assets/3faa1e61-08a8-488c-96df-7430b24eb67c" />


### Image Cropping

<img width="358" height="290" alt="image" src="https://github.com/user-attachments/assets/e772d88d-c561-4718-b991-4c1c33096a1c" />


---

## Result

Thus, various geometric transformations such as translation, scaling, shearing, reflection, rotation, and cropping are successfully performed using OpenCV.
