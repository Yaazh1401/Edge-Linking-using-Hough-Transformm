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
## Output

### Input image
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("C:\\Users\\admin\\OneDrive\\Desktop\\DIPT\\flwr.jpeg")  
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB)) 
plt.title("Input Image")
plt.axis('off')
```

<img width="830" height="520" alt="image" src="https://github.com/user-attachments/assets/785ba966-5724-4881-83ea-1c20f1369b1e" />

### grayscale image
```
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
```

<img width="780" height="537" alt="image" src="https://github.com/user-attachments/assets/53b00a38-1626-4b94-8cdc-298c479c0373" />


### Canny Edge detector output
```

edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')

```

<img width="860" height="545" alt="image" src="https://github.com/user-attachments/assets/ce5571b6-a863-4056-a507-0ad966b5a6d3" />



### Display the result of Hough transform

```

lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)
for line in lines:
    x1, y1, x2, y2 = line[0]  
    cv2.line(image, (x1, y1), (x2, y2), (90, 250, 79), 2)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Result of Hough Transform")
plt.axis('off')

```

<img width="875" height="514" alt="image" src="https://github.com/user-attachments/assets/85172197-3c33-482b-b80e-902a3955ea5e" />


## RESULT :
Thus,The Python program to detect the lines using Hough Transform run successfully.
