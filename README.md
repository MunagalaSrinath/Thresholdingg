## THRESHOLDING
### Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

### Software Required
1. Anaconda - Python 3.7
2. OpenCV

### Algorithm

#### Step1:
Load the necessary packages.
#### Step2:
Read the Image and convert to grayscale.
#### Step3:
Use Global thresholding to segment the image.
#### Step4:
Use Adaptive thresholding to segment the image.
#### Step5:
Use Otsu's method to segment the image and display the results.

### Program
```python
DEVELOPED BY: ARVIND S
REGISTER NO: 212222240012
```
#### Load the necessary packages
```python
import numpy as np
import matplotlib.pyplot as plt
import cv2
```
#### Read the Image and convert to grayscale
```python
image = cv2.imread("ddd.jpg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("ddd.jpg",0)
```
#### Use Global thresholding to segment the image
```python
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
#### Use Adaptive thresholding to segment the image
```python
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
#### Use Otsu's method to segment the image 
```python
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
#### Display the results
```
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
for i in range(0,9):
    plt.figure(figsize=(10,10))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()
```
### Output
#### Original Image
![image](https://github.com/MunagalaSrinath/Thresholdingg/assets/118678482/e84a5c48-ef0e-445f-a769-192ab4121740)

#### Global Thresholding
![image](https://github.com/MunagalaSrinath/Thresholdingg/assets/118678482/3ab053e4-1c89-4ec0-83d8-57fc6570a33b)
![image](https://github.com/MunagalaSrinath/Thresholdingg/assets/118678482/63bf0843-ccbc-4491-87a7-ef23016d468c)
![image](https://github.com/MunagalaSrinath/Thresholdingg/assets/118678482/ca1535b3-381e-4682-b412-b878996e7c7d)
![image](https://github.com/MunagalaSrinath/Thresholdingg/assets/118678482/bc48994b-944d-4bca-99e3-bcb28b4decc4)
![image](https://github.com/MunagalaSrinath/Thresholdingg/assets/118678482/686cd685-ab09-43f9-a35a-1f046293379d)

#### Adaptive Thresholding
![image](https://github.com/MunagalaSrinath/Thresholdingg/assets/118678482/f21e3104-5269-4f3b-84fc-d3d5ddc91a8f)
![image](https://github.com/MunagalaSrinath/Thresholdingg/assets/118678482/8e18db89-f108-442c-8d71-bfd18e3c4547)

#### Optimum Global Thesholding using Otsu's Method
![image](https://github.com/MunagalaSrinath/Thresholdingg/assets/118678482/bb5a37dc-0d1d-4969-b083-0715154c39a3)

### Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
