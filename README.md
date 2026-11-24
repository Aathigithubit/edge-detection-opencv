# edge-detection-opencv

## Aim

To perform edge detection using Sobel, Roberts, Prewitt, Laplacian, and Canny edge detectors.

---

## Software Required

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (cv2)  
- NumPy  
- Matplotlib  

---

## ⚙️ Algorithm

### Step 1:
Import all the necessary modules for the program.

### Step 2:
Load an image using `cv2.imread()`.

### Step 3:
Convert the image to grayscale.

### Step 4:
Apply **Sobel operator** using OpenCV to detect edges.

### Step 5:
Apply **Prewitt operator** using custom kernels.

### Step 6:
Apply **Roberts operator** using custom kernels.

### Step 7:
Apply **Laplacian operator** using OpenCV.

### Step 8:
Apply **Canny edge detector** using OpenCV.

### Step 9:
Display all edge-detected images for comparison.

---
## PROGRAM

## Developed By

- **Name:** ________AATHI S____________________  
- **Register No:** ___212223220001___________________  
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('img.jpg')  # Replace with your image path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
# Original Image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')
(np.float64(-0.5), np.float64(1079.5), np.float64(1281.5), np.float64(-0.5))

sobel_x = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=5)  # Sobel in x direction
sobel_y = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=5)  # Sobel in y direction
sobel_combined = cv2.magnitude(sobel_x, sobel_y)  # Combine both directions
plt.imshow(sobel_combined, cmap='gray')
plt.title('Sobel Edge Detection')
plt.axis('off')
(np.float64(-0.5), np.float64(1079.5), np.float64(1281.5), np.float64(-0.5))

laplacian = cv2.Laplacian(gray_image, cv2.CV_64F)
plt.imshow(laplacian, cmap='gray')
plt.title('Laplacian Edge Detection')
plt.axis('off')
(np.float64(-0.5), np.float64(1079.5), np.float64(1281.5), np.float64(-0.5))

canny_edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off')  
(np.float64(-0.5), np.float64(1079.5), np.float64(1281.5), np.float64(-0.5))

 
```
---

## Output

###  Sobel Edge Detector
- Detects edges in horizontal and vertical directions  
- Produces gradient-based edge map  
<img width="465" height="540" alt="image" src="https://github.com/user-attachments/assets/21ba0345-2f04-4e86-ae44-02fe41936499" />
<img width="486" height="508" alt="image" src="https://github.com/user-attachments/assets/2b2cc710-11a1-416b-a8d8-44f606b2b0de" />

###  Laplacian Edge Detector
- Detects edges using second-order derivatives  
- Highlights rapid intensity changes  
<img width="472" height="520" alt="image" src="https://github.com/user-attachments/assets/e66de229-8735-4d0e-a3d9-f1afdc2b856a" />

###  Canny Edge Detector
- Multi-stage edge detection  
- Produces clean and thin edges  
<img width="446" height="520" alt="image" src="https://github.com/user-attachments/assets/b4973836-e0ad-4db2-b2a7-7eefec7596c8" />

---

## Result

Thus, edges are successfully detected using Sobel, Prewitt, Roberts, Laplacian, and Canny edge detection techniques. Each method highlights edges differently based on gradient and intensity variations, improving feature extraction and analysis.
