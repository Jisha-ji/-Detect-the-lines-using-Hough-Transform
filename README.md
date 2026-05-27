# EX. NO 7  : Detect-the-lines-using-Hough-Transform


##  Aim

To implement a basic lane detection pipeline using OpenCV by completing missing code segments at specified locations.

##  Software Used

* Anaconda – Python 3.7
* Jupyter Notebook / VS Code
* OpenCV (cv2)
* NumPy
* Matplotlib
  
##  Algorithm & Explanation

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

## PROGRAM 

### NAME: JISHA BOSSNE SJ
### REG NO: 212224230106

### Step 1: Import the neccessary libraries
```
    import cv2
    import numpy as np
    import matplotlib.pyplot as plt
```
### Step 2: Load the image using imread() from cv2 module
```
    image = cv2.imread('lan_img1.jpg')  # Replace 'image.jpg' with your image path
```    
### Step 3: Convert the image to grayscale
```
    gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
    # Input image and grayscale image
    plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert image to RGB for displaying
    plt.title("Input Image")
    plt.axis('off')
    plt.imshow(gray_image, cmap='gray')
    plt.title("Grayscale Image")
    plt.axis('off')
```    
### Step 4: Using Canny operator from cv2, detect the edges of the image
```
    edges = cv2.Canny(gray_image, 50, 150)  # Canny edge detection with threshold values 50 and 150
```    
### Canny Edge Detector output
```
    plt.imshow(edges, cmap='gray')
    plt.title("Canny Edge Detector")
    plt.axis('off')
```    
### Step 5: Using the HoughLinesP(), detect line coordinates for every point in the image
```
    # The parameters of HoughLinesP are: image, resolution, threshold, minLineLength, maxLineGap
    lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)
```
### Step 6: Using a for loop, draw the lines on the original image using the detected coordinates
```
    for line in lines:
        x1, y1, x2, y2 = line[0]  # Unpacking the line coordinates
        cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)  # Draw green lines with thickness of 2
 ```       
### Display the result of Hough Transform (Image with lines)
```
    plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Image with lines drawn
    plt.title("Result of Hough Transform")
    plt.axis('off')
```
##  Expected Output

### Original image
<img width="688" height="508" alt="image" src="https://github.com/user-attachments/assets/e58393c6-51f9-4283-9525-4f6f5a0c00a7" />

### Grayscale image
<img width="706" height="501" alt="image" src="https://github.com/user-attachments/assets/85b59707-b1dd-44d7-b846-ebb611b25b6f" />

### Edge detected image
<img width="685" height="511" alt="image" src="https://github.com/user-attachments/assets/a5dc88a4-4070-42fd-8182-5ef16c45472c" />

### Result of Hough Transform
<img width="670" height="525" alt="image" src="https://github.com/user-attachments/assets/48b10720-32a5-4bd4-b7cd-12e9ab9fbb55" />

## Result

Thus, the lane detection pipeline is successfully implemented by completing the missing code sections. The system detects and highlights lane lines effectively.
