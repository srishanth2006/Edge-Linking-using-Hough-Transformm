# Edge-Linking-using-Hough-Transformm


## Developed By: SRISHANTH J
## Reg.No.: 212223240160

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

### Program
```
NAME:SRISHANTH J
REG NO : 212223240160

import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('chessboard.png')
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert image to RGB for displaying
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
    x1, y1, x2, y2 = line[0]  # Unpacking the line coordinates
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Image with lines drawn
plt.title("Result of Hough Transform")
plt.axis('off')
```

## Output

### Input image and grayscale image

![image](https://github.com/user-attachments/assets/a657271a-350f-4eb8-8353-a7845865412a)

![image](https://github.com/user-attachments/assets/55a9da73-f9bc-4be1-b8d0-6d9aa0f3a4b4)

### Canny Edge detector output

![image](https://github.com/user-attachments/assets/1b1ca57a-6416-489c-9c8c-2c3016e19df8)

### Display the result of Hough transform

![image](https://github.com/user-attachments/assets/ae4ea77e-cfd0-47b6-93b7-109c75736f70)

### Result:

Thus the grayscale image , canny edge detector and hence we had displayed the result of hough transform
