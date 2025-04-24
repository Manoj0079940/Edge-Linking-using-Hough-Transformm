# Edge-Linking-using-Hough-Transformm
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:

Import all the necessary modules for the program.
### Step2:

Load a image using imread() from cv2 module.
### Step3:

Convert the image to grayscale.
### Step4:

Using Canny operator from cv2,detect the edges of the image.
### Step5:

Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.
## code
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('Qn_7_.jpg')

gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  
plt.title("Input Image")
plt.axis('off')

plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')

edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')

lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)

for line in lines:
    x1, y1, x2, y2 = line[0]  
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2) 

plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB)) 
plt.title("Result of Hough Transform")
plt.axis('off')
```
## Output

### Input image and grayscale image
![image](https://github.com/user-attachments/assets/897714b5-a7e7-4ba7-bf87-347e870b7f12)
![image-1](https://github.com/user-attachments/assets/42dec9d5-25bf-4ae1-a50b-121622daedea)



### Canny Edge detector output
![image-2](https://github.com/user-attachments/assets/4c1877c3-9071-47e2-914d-f346f6d28a92)

### Display the result of Hough transform
![image-3](https://github.com/user-attachments/assets/054f6319-b66e-442e-b266-73be8d372e37)

## Result
Thus,The Python program to detect the lines using Hough Transform run successfully.
