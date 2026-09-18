## Exp-10--Record-IMPLEMENTATION-OF-OPENING-AND-CLOSING
# DIPT-EXP-10-IMPLEMENTATION-OF-OPENING-AND-CLOSING

# Name : Vignesh.P
# Reg.no: 212224230302
## Aim

To write a Python program using OpenCV to perform morphological Opening and Closing operations on an image.

The program performs the following operations:

- Morphological Opening
- Morphological Closing

## Software Used

- Anaconda – Python 3.7
- Jupyter Notebook / VS Code
- OpenCV (cv2)
- NumPy
- Matplotlib

## Algorithm

### Step 1:

Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:

Create or load an input image containing foreground objects.

### Step 3:

Display the original image.

### Step 4:

Create a structuring element (kernel) of suitable size.

### Step 5: Opening Operation

- Apply the Opening operation using the structuring element.
- Opening consists of Erosion followed by Dilation.
- Remove small foreground noises while preserving the shape of larger objects.
- Display the opened image.

### Step 6: Closing Operation

- Apply the Closing operation using the structuring element.
- Closing consists of Dilation followed by Erosion.
- Fill small holes and gaps within foreground objects.
- Display the closed image.

### Step 7:

Compare the original, opened, and closed images.


## PROGRAM


### Original Image

```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = np.zeros((500, 500, 3), dtype=np.uint8)
font = cv2.FONT_HERSHEY_SIMPLEX
cv2.putText(image, 'Gokul S ', (100, 250), font, 1, (255, 255, 255), 2, cv2.LINE_AA)
kernel = np.ones((3, 3), np.uint8)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB for displaying
plt.title("Input Image with Text")
plt.axis('off')

```
<img width="389" height="410" alt="download" src="https://github.com/user-attachments/assets/a22cac8c-f550-47c9-a9a9-caa318f9b949" />


### Opening Operation
```
opened_image = cv2.morphologyEx(image, cv2.MORPH_OPEN, kernel)
plt.imshow(cv2.cvtColor(opened_image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB
plt.title("Opening Operation")
plt.axis('off')
```
<img width="389" height="410" alt="download" src="https://github.com/user-attachments/assets/1080fbae-0515-4f7d-b55b-52c98424b5f4" />



### Closing Operation
```
closing = cv2.morphologyEx(image, cv2.MORPH_CLOSE, kernel)
plt.imshow(cv2.cvtColor(closing, cv2.COLOR_BGR2RGB))
plt.title("Closing")
plt.axis("off")

```

<img width="389" height="410" alt="download" src="https://github.com/user-attachments/assets/ad158c9e-1a90-4ffb-abf1-2b8a0776296f" />


## Applications

### Opening

- Noise removal in binary images.
- Separation of connected objects.
- Preprocessing for object detection.

### Closing

- Filling small holes in objects.
- Connecting nearby components.
- Enhancing segmented regions.

## Advantages

### Opening

- Removes unwanted foreground noise.
- Preserves major object structures.
- Improves segmentation quality.

### Closing

- Restores object continuity.
- Eliminates small background gaps.
- Improves object representation.

## Result

Thus, the morphological operations **Opening** and **Closing** are successfully implemented using OpenCV. 
