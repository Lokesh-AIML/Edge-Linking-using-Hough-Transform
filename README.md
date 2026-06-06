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
## Program

### Developed By : Lokeshwaran S
### Register No : 212224240080

### Input image and grayscale image
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```
```
# Step 2: Load the image using imread() from cv2 module
image = cv2.imread(r"C:\Users\waran\Downloads\tiger.jpg")  # Replace 'image.jpg' with your image path
```
```
# Step 3: Convert the image to grayscale
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
```
```
# Input image and grayscale image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert image to RGB for displaying
plt.title("Input Image")
plt.axis('off')
```

<img width="653" height="424" alt="image" src="https://github.com/user-attachments/assets/795230c1-2705-486d-b409-5959d400a72c" />

```
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
```

<img width="656" height="424" alt="image" src="https://github.com/user-attachments/assets/84834bcf-7a9b-4b27-86c8-2ab088f94acc" />


### Canny Edge detector output

```
# Step 4: Using Canny operator from cv2, detect the edges of the image
edges = cv2.Canny(gray_image, 50, 150)  # Canny edge detection with threshold values 50 and 150
```
```
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
```
<img width="654" height="456" alt="image" src="https://github.com/user-attachments/assets/ada0c95e-35dc-45ce-928b-85b72897ac3f" />


### Display the result of Hough transform

```
# Step 5: Using the HoughLinesP(), detect line coordinates for every point in the image
# The parameters of HoughLinesP are: image, resolution, threshold, minLineLength, maxLineGap
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)
```
```
# Step 6: Using a for loop, draw the lines on the original image using the detected coordinates
# The lines variable contains the endpoints of the detected lines
for line in lines:
    x1, y1, x2, y2 = line[0]  # Unpacking the line coordinates
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)  # Draw green lines with thickness of 2
```
```
# Display the result of Hough Transform (Image with lines)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Image with lines drawn
plt.title("Result of Hough Transform")
plt.axis('off')
```
<img width="655" height="450" alt="image" src="https://github.com/user-attachments/assets/5c626230-48e1-497b-b49b-00229e279863" />

### Result:
Thus,The Python program to detect the lines using Hough Transform run successfully.


