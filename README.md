# DIPT-Workshop-4

## Coin-Detection-using-OpenCV-in-Python
## Name : AJAY S
## Reg.no : 21224230010

```
import cv2
import matplotlib.pyplot as plt
import numpy as np
image = cv2.imread('CoinsA.png')
imageCopy = image.copy()
plt.imshow(image[:,:,::-1]);
plt.title("Original Image")
plt.show()
plt.figure(figsize=(12,12))
plt.subplot(121);plt.imshow(image[:,:,::-1]);plt.title("Original Image")
plt.subplot(122); plt.imshow(imageGray,cmap='gray');plt.title("Grayscale Image"); plt.show()
plt.figure(figsize=(20,12))
plt.subplot(141);plt.imshow(image[:,:,::-1]);plt.title("Original Image")
plt.subplot(142);plt.imshow(imageB,cmap='gray');plt.title("Blue Channel")
plt.subplot(143);plt.imshow(imageG,cmap='gray');plt.title("Green Channel")
plt.subplot(144);plt.imshow(imageR,cmap='gray');plt.title("Red Channel");
plt.show()
thresh =20
maxValue = 255
th, dst_bin_inv = cv2.threshold(imageG, thresh, maxValue, cv2.THRESH_BINARY_INV)
plt.imshow(dst_bin_inv, cmap='gray', vmin=0, vmax=255)
plt.title("Threshold Binary Inverse");
kSize = (5,5)
kernel2 = cv2.getStructuringElement(cv2.MORPH_ELLIPSE, kSize)
imageDilated2 = cv2.dilate(dst_bin_inv, kernel2, iterations=2)
plt.imshow(imageDilated2,cmap='gray')
plt.title('Dilated Image Iteration 2')
plt.show()
kSize = (11,11)
kernel1 = cv2.getStructuringElement(cv2.MORPH_ELLIPSE, kSize)
imageEroded = cv2.erode(imageDilated2, kernel1)
plt.imshow(imageEroded,cmap='gray')
plt.title("Eroded Image")
plt.show()
# Set up the SimpleBlobdetector with default parameters.
params = cv2.SimpleBlobDetector_Params()

params.blobColor = 0

params.minDistBetweenBlobs = 2

# Filter by Area.
params.filterByArea = False

# Filter by Circularity
params.filterByCircularity = True
params.minCircularity = 0.8

# Filter by Convexity
params.filterByConvexity = True
params.minConvexity = 0.8

# Filter by Inertia
params.filterByInertia =True
params.minInertiaRatio = 0.8
```
### OUTPUT:

<img width="392" height="433" alt="download" src="https://github.com/user-attachments/assets/fa4aa0fd-f66a-4ff3-a21a-4072f7efcbdb" />

<img width="986" height="528" alt="download" src="https://github.com/user-attachments/assets/e07e70cd-1ca8-4a0d-99f4-a04454ea9382" />

<img width="1606" height="434" alt="download" src="https://github.com/user-attachments/assets/b2534621-d393-4060-9d5b-46583705b45c" />

<img width="392" height="433" alt="download" src="https://github.com/user-attachments/assets/ee0055e8-94a7-4664-b993-3fa340c467f0" />

<img width="392" height="433" alt="download" src="https://github.com/user-attachments/assets/5e416912-3be4-4bc6-b5be-5b9230d3d309" />

<img width="392" height="433" alt="download" src="https://github.com/user-attachments/assets/9a2a860d-807b-409e-baff-1b19b332a808" />

### RESULT :

Thus Coin-Detection-using-OpenCV-in-Python Done successfully.
