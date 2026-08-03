# Geometric Transformations Using OpenCV

---

## Aim

To write a Python program using OpenCV to perform various geometric transformations on an image.

The program performs the following operations:

- Image Translation  
- Image Scaling (Resizing)  
- Image Shearing  
- Image Reflection (Flipping)  
- Image Rotation  

---

##  Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib  

---

##  Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the input image in color mode.

### Step 3: Image Translation
- Create a translation matrix to shift the image  
- Move the image 50 pixels to the right and 80 pixels down  
- Apply transformation using `cv2.warpAffine()`  
- Display original and translated images  

### Step 4: Image Scaling
- Resize the image to 0.5× (downscale)  
- Resize the image to 2× (upscale)  
- Use `cv2.resize()`  
- Display original, downscaled, and upscaled images  

### Step 5: Image Shearing
- Create transformation matrices for:
  - Horizontal shearing  
  - Vertical shearing  
- Apply transformations using `cv2.warpAffine()`  
- Display original and sheared images  

### Step 6: Image Reflection
- Perform flipping using `cv2.flip()`:
  - Horizontal reflection  
  - Vertical reflection  
  - Both axes  
- Display all reflected images  

### Step 7: Image Rotation
- Create rotation matrices for:
  - 45° rotation  
  - 90° rotation  
- Use `cv2.getRotationMatrix2D()` and `cv2.warpAffine()`  
- Display original and rotated images  

---

##  Program
~~~
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('superman.jpg') 

plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB)) 
plt.title("Original Image")  
plt.axis('off')
~~~

~~~
tx, ty = 100, 50 
M_translation = np.float32([[1, 0, tx], [0, 1, ty]])  

translated_image = cv2.warpAffine(image, M_translation, (image.shape[1], image.shape[0])) 
plt.imshow(cv2.cvtColor(translated_image, cv2.COLOR_BGR2RGB))  
plt.title("Translated Image")  
plt.axis('off')

~~~

~~~
fx, fy = 5.0, 2.0  
scaled_image = cv2.resize(image, None, fx=fx, fy=fy, interpolation=cv2.INTER_LINEAR)
plt.imshow(cv2.cvtColor(scaled_image, cv2.COLOR_BGR2RGB))  
plt.title("Scaled Image")  
plt.axis('off')

~~~
~~~
shear_matrix = np.float32([[1, 0.5, 0], [0.5, 1, 0]]) 
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))
plt.imshow(cv2.cvtColor(sheared_image, cv2.COLOR_BGR2RGB)) 
plt.title("Sheared Image")  
plt.axis('off')
~~~

~~~
reflected_image = cv2.flip(image, 2) 
plt.imshow(cv2.cvtColor(reflected_image, cv2.COLOR_BGR2RGB))
plt.title("Reflected Image")  
plt.axis('off')
~~~

~~~
(height, width) = image.shape[:2] 
angle = 45 
center = (width // 2, height // 2)  
M_rotation = cv2.getRotationMatrix2D(center, angle, 1)  
rotated_image = cv2.warpAffine(image, M_rotation, (width, height))  
plt.imshow(cv2.cvtColor(rotated_image, cv2.COLOR_BGR2RGB))
plt.title("Rotated Image")  
plt.axis('off')
~~~

~~~
x, y, w, h = 100, 200, 200, 150  
cropped_image = image[y:y+h, x:x+w]
plt.imshow(cv2.cvtColor(cropped_image, cv2.COLOR_BGR2RGB))  
plt.title("Cropped Image")  
plt.axis('off')

~~~






### Developed By:
**Name:G.N Vishnuram** 

### Register No:
212225240187
---

##  Output

### Original image
<img width="296" height="325" alt="image" src="https://github.com/user-attachments/assets/f4dcb6bd-5efd-4ce3-8d56-780df1cbb321" />


### Image Translation
<img width="302" height="331" alt="image" src="https://github.com/user-attachments/assets/6d8cc0b6-0156-4baa-908e-4c35f9eeaa54" />


### Image Scaling
<img width="423" height="188" alt="image" src="https://github.com/user-attachments/assets/cbe282c0-66fd-46ba-b08d-45b48df143c3" />

### Image Shearing

<img width="299" height="328" alt="image" src="https://github.com/user-attachments/assets/44842a8f-55c2-46bb-b3e0-4abd4a029a06" />

### Image Reflection

<img width="301" height="330" alt="image" src="https://github.com/user-attachments/assets/c577f950-6a60-4ebf-88a7-d3d234bc7983" />

### Image Rotation
<img width="294" height="321" alt="image" src="https://github.com/user-attachments/assets/a3f5ee31-ca6c-48c6-a5b6-8c37e3d8c7b4" />

### Image Crop
<img width="405" height="312" alt="image" src="https://github.com/user-attachments/assets/613a9a1c-8ef8-497c-845f-aefe88cd7e55" />

---

##  Result

Thus, various geometric transformations such as translation, scaling, shearing, reflection, and rotation are successfully performed using OpenCV. These transformations demonstrate how images can be spatially manipulated for different computer vision applications.
