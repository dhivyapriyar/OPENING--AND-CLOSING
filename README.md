# OPENING--AND-CLOSING
## Aim
To implement Opening and Closing using Python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
### Step1:
Load the input image using cv2.imread().

### Step2:
Define a structuring element (e.g., 5x5 rectangular) using cv2.getStructuringElement().

### Step3:
Perform erosion followed by dilation using cv2.morphologyEx() with the cv2.MORPH_OPEN operation.

### Step4:
Perform dilation followed by erosion using cv2.morphologyEx() with the cv2.MORPH_CLOSE operation.

### Step5:
Use plt.subplot() to show the original, opening, and closing images side by side.
## Program:
### Name: Dhivyapriya. R
### Register No.: 212222230032
# Import the necessary packages
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```
# Create a blank image
```
image = np.zeros((300, 600, 3), dtype="uint8")
```
# Create the Text using cv2.putText
```
text = "OpenCV Demo"
font = cv2.FONT_HERSHEY_SIMPLEX
cv2.putText(image, text, (50, 150), font, 2, (255, 255, 255), 3)
```
# Create the structuring element
```
kernel = cv2.getStructuringElement(cv2.MORPH_RECT, (5, 5))
```
# Use Opening operation
```
opening_image = cv2.morphologyEx(image, cv2.MORPH_OPEN, kernel)
```

# Use Closing Operation
```
closing_image = cv2.morphologyEx(image, cv2.MORPH_CLOSE, kernel)
```
# Convert images from BGR to RGB for Matplotlib
```
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
opening_image_rgb = cv2.cvtColor(opening_image, cv2.COLOR_BGR2RGB)
closing_image_rgb = cv2.cvtColor(closing_image, cv2.COLOR_BGR2RGB)
```

# Plot the original, opening, and closing images using Matplotlib
```
plt.figure(figsize=(10, 5))

plt.subplot(1, 3, 1)
plt.imshow(image_rgb)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1, 3, 2)
plt.imshow(opening_image_rgb)
plt.title("Opening Operation")
plt.axis("off")

plt.subplot(1, 3, 3)
plt.imshow(closing_image_rgb)
plt.title("Closing Operation")
plt.axis("off")

plt.tight_layout()
plt.show()


```
## Output:

### Display the input Image

![image](https://github.com/user-attachments/assets/a75b89ff-1c8a-479a-86b0-85faa1f7ca94)


### Display the result of Opening

![image](https://github.com/user-attachments/assets/5b68db40-7046-4553-a8e9-b9dff612b15e)


### Display the result of Closing
![image](https://github.com/user-attachments/assets/b1f357bd-1b6c-44fc-88bd-8f6c8788ee0d)


## Result
Thus the Opening and Closing operation is used in the image using python and OpenCV.
