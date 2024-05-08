# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the necessary packages.

### Step2:
Read the Image and convert to grayscale.

### Step3:
Use Global thresholding to segment the image.

### Step4:
Use Adaptive thresholding to segment the image.

### Step5:
Use Otsu's method to segment the image and display the results.

## Program
```
Developed By : SWETHA S
Register Number : 212222230155
```
# Load the necessary packages
```
import numpy as np
import matplotlib.pyplot as plt
import cv2
```
# Read the Image and convert to grayscale
```
image = cv2.imread('dog.jpg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('dog.jpg',0)
```
# Use Global thresholding to segment the image
```
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
# Use Adaptive thresholding to segment the image
```
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
# Use Otsu's method to segment the image 
```
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```

# Display the results
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

## Output

### Original Image
![image](https://github.com/swethaselvarajm/Thresholdingg/assets/119525603/e543cecf-6da3-432c-8a15-0220355a5f43)


### Global Thresholding
![image](https://github.com/swethaselvarajm/Thresholdingg/assets/119525603/850a1c48-11f8-4e3c-a064-cba9337dfc92)
![image](https://github.com/swethaselvarajm/Thresholdingg/assets/119525603/1349fb84-3c49-4560-be2e-89d820d1e36c)
![image](https://github.com/swethaselvarajm/Thresholdingg/assets/119525603/19fdbd34-28f4-4254-9bc6-ea8a854a97f7)
![image](https://github.com/swethaselvarajm/Thresholdingg/assets/119525603/03e6c256-f45f-4ec1-978d-30fc94be39f9)
![image](https://github.com/swethaselvarajm/Thresholdingg/assets/119525603/10114896-02f1-46c9-bc87-da6d56a3e3e7)



### Adaptive Thresholding
![image](https://github.com/swethaselvarajm/Thresholdingg/assets/119525603/ace1d25f-294a-4b9d-8d0c-a5156409d09f)

![image](https://github.com/swethaselvarajm/Thresholdingg/assets/119525603/c9e8e0d5-547a-490f-80ca-6dc5c4d4bd52)

### Optimum Global Thesholding using Otsu's Method
![image](https://github.com/swethaselvarajm/Thresholdingg/assets/119525603/674a670f-831d-4237-aa47-eee12020ac9d)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
