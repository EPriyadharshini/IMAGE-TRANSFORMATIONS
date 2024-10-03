![image](https://github.com/user-attachments/assets/b7ebe89f-d40e-4747-9cd9-f74a9975d41e)# IMAGE-TRANSFORMATIONS

## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:


Step1:
Import the necessary libraries and read the original image and save it as a image variable.

Step2:
Translate the image using a function warpPerpective()

Step3:
Scale the image by multiplying the rows and columns with a float value.

Step4:
Shear the image in both the rows and columns.

Step5:
Find the reflection of the image.

Step6:
Rotate the image using angle function.


## Program:
```

Developed By:PRIYADHARSHINI E
Register Number:212223230159

import cv2
import numpy as np
import matplotlib.pyplot as plt

## ORGINAL IMAGE

image = cv2.imread('POKE2.jpeg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)  

# Convert BGR to RGB for Matplotlib
plt.imshow(image_rgb)
plt.title("Original Image")
plt.axis('off')


```
i)Image Translation

rows, cols, _ = image.shape
M_translate = np.float32([[1, 0, 60], [0, 1, 55]])  
# Translate by (50, 100) pixels
translated_image = cv2.warpAffine(image_rgb, M_translate, (cols, rows))
plt.imshow(translated_image)
plt.title("Translated Image")
plt.axis('off')



ii) Image Scaling & Image shearing


M_shear = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  # Shear with factor 0.5
shared_image = cv2.warpAffine(image_rgb, M_shear, (int(cols* 1.5), int(rows * 1.5)))
plt.imshow(shared_image)
plt.title("Shared Image")
plt.axis('off')


iv)Image Reflection

reflected_image = cv2.flip(image_rgb, 1)  # Horizontal reflection (flip along y-axis)
plt.imshow(reflected_image)
plt.title("Reflected Image")
plt.axis('off')



v)Image Rotation

M_rotate = cv2.getRotationMatrix2D((cols / 2, rows / 2), 45, 1)  # Rotate by 45 degrees
rotated_image = cv2.warpAffine(image_rgb, M_rotate, (cols, rows))
plt.imshow(rotated_image)
plt.title("Rotated Image")
plt.axis('off')



vi)Image Cropping

cropped_image = image_rgb[50:200, 50:300]  # Crop a portion of the image
plt.figure(figsize=(4, 4))
plt.imshow(cropped_image)
plt.title("Cropped Image")
plt.axis('off')
plt.show()



```
## Output:

![image](https://github.com/user-attachments/assets/d5b09b72-631f-4355-9d1c-3d699fb1b5c4)

### i)Image Translation

![image](https://github.com/user-attachments/assets/7e8c55ae-c689-4f2f-8187-233cf9ad2b30)


### ii) Image Scaling &shering


![image](https://github.com/user-attachments/assets/9bcd8bc5-3d1c-4c3a-a0ae-97cab22b6d1a)


### iv)Image Reflection

![image](https://github.com/user-attachments/assets/65e4ee39-5a11-45be-9c3b-b96787daf0e5)


### v)Image Rotation

![image](https://github.com/user-attachments/assets/c6d41339-0f25-42d7-8141-4ee8caec740f)


### vi)Image Cropping

![image](https://github.com/user-attachments/assets/8722374f-91ab-41fd-bc28-6513c521c791)


## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
