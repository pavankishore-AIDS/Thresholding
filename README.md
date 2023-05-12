# Thresholding of Images
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Import required packages

### Step2:
Import the image to operate on

### Step3:
Convert the image to grayscale image.

### Step4:
Apply threshold operators on the image.
### Step5:

Display the output.
## Program


## Developed : Pavan Kishore.M
## Reg : 212221230076
```python 3
# Load the necessary packages:
import cv2
import numpy as np
import matplotlib.pyplot as plt


# Read the Image and convert to grayscale:
image=cv2.imread("tes.jpg",1)
image=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray=cv2.imread("tes.jpg",0)


# Use Global thresholding to segment the image:
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)


# Use Adaptive thresholding to segment the image:
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)


# Use Otsu's method to segment the image:
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)


# Display the results:
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
for i in range(0,9):
    plt.figure(figsize=(5,5))
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
## Output
### Original Image
![a1](https://github.com/pavankishore-AIDS/Thresholding/assets/94154941/7daaa853-cd30-4f16-957f-d302ed9aa3ad)
### Global Thresholding
![a2](https://github.com/pavankishore-AIDS/Thresholding/assets/94154941/cd96b54a-ca05-4f1a-b708-8355bc6e7746)
![a3](https://github.com/pavankishore-AIDS/Thresholding/assets/94154941/d26c5033-efec-47dd-9eee-00d974e7041f)
![a4](https://github.com/pavankishore-AIDS/Thresholding/assets/94154941/fc6e5977-d39e-455e-9b1e-a1950fdcf901)
![a5](https://github.com/pavankishore-AIDS/Thresholding/assets/94154941/e4776502-fc01-4f12-baf8-09a1e2416c0b)
![a6](https://github.com/pavankishore-AIDS/Thresholding/assets/94154941/de12ea6c-56ba-40a3-8e67-742831933db4)

### Adaptive Thresholding
![a7](https://github.com/pavankishore-AIDS/Thresholding/assets/94154941/515da1f7-e1e2-4fe7-bf84-c7629a8d8216)
![a8](https://github.com/pavankishore-AIDS/Thresholding/assets/94154941/81a4e268-bd4c-40e4-81bf-a6d222026fb8)

### Optimum Global Thesholding using Otsu's Method
![a9](https://github.com/pavankishore-AIDS/Thresholding/assets/94154941/3516d7ec-ca8f-4533-80be-433244718277)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
