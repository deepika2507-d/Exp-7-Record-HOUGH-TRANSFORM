# Exp-7-Record-HOUGH-TRANSFORM
Edge-Linking-using-Hough-Transform

NAME : DEEPIKA V

REG NO : 212224240030

Aim:

To write a Python program to detect the lines using Hough Transform.

Software Required:

Anaconda - Python 3.7

Algorithm:

Step1: Import all the necessary modules for the program.

Step2: Load a image using imread() from cv2 module.

Step3: Convert the image to grayscale.

Step4: Using Canny operator from cv2,detect the edges of the image.

Step5: Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.

Program

Input image
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('pic.jpeg')

gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Input Image")
plt.axis('off')
```
grayscale image
```
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
```
Canny Edge detector output
```
edges = cv2.Canny(gray_image, 50, 150)

plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
```
Display the result of Hough transform

```
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)

for line in lines:
    x1, y1, x2, y2 = line[0]
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)

plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Result of Hough Transform")
plt.axis('off')
```
Output:
Input image and grayscale image

<img width="263" height="406" alt="image" src="https://github.com/user-attachments/assets/9bfb4284-3fd1-4b5e-a18b-4bae4dadb21b" />

<img width="248" height="402" alt="image" src="https://github.com/user-attachments/assets/a1df682f-3cb3-4d00-a104-0a2c57607ca4" />

Canny Edge detector output

<img width="269" height="407" alt="image" src="https://github.com/user-attachments/assets/8ec9a60f-30a1-4c09-8ab7-cc2b058ee4a8" />

Display the result of Hough transform

<img width="284" height="407" alt="image" src="https://github.com/user-attachments/assets/a60239bf-44ba-441f-9f3f-f60451524b2c" />


Result:

Thus, the lane detection pipeline is successfully implemented by completing the missing code sections. The system detects and highlights lane lines effectively.
