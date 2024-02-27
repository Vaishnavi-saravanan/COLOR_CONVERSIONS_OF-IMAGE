### EX-01 COLOR_CONVERSIONS_OF-IMAGE
# AIM
To write a python program using OpenCV to do the following image manipulations.

i) Read, display, and write an image.

ii) Access the rows and columns in an image.

iii) Cut and paste a small portion of the image.

iv)To perform the color conversion between RGB, BGR, HSV, and YCbCr color models.

# Software Required:
# Anaconda - Python 3.7

# Algorithm:
Step1: Choose an image and save it as a filename.jpg ,
Step2: Use imread(filename, flags) to read the file.
Step3: Use imshow(window_name, image) to display the image.
Step4: Use imwrite(filename, image) to write the image.
Step5: End the program and close the output image windows.
Step6: Convert BGR and RGB to HSV and GRAY
Step7: Convert HSV to RGB and BGR
Step8: Convert RGB and BGR to YCrCb
Step9: Split and Merge RGB Image
Step10: Split and merge HSV Image
### Program:
### Developed By: VAISHNAVI S
### Register Number: 212222230165
## i) Read and display the image
```
import cv2
image=cv2.imread('cat.jpg')
cv2.imshow('VAISHNAVI',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
# OUTPUT:
![Screenshot 2024-02-27 210459](https://github.com/Vaishnavi-saravanan/COLOR_CONVERSIONS_OF-IMAGE/assets/118541897/0963c23c-25d6-481c-8802-af6197123b4e)


# ii)Write the image
```
import cv2
image=cv2.imread('cat.jpg',0)
cv2.imwrite('demos.jpg',image)
```
# OUTPUT:

![Screenshot 2024-02-27 214245](https://github.com/Vaishnavi-saravanan/COLOR_CONVERSIONS_OF-IMAGE/assets/118541897/1976a092-1ea6-4d0c-9b53-b52056d544ef)

# iii)Shape of the Image
```
import cv2
image=cv2.imread('cat.jpg',1)
print(image.shape)
```
# OUTPUT:
![Screenshot 2024-02-27 214255](https://github.com/Vaishnavi-saravanan/COLOR_CONVERSIONS_OF-IMAGE/assets/118541897/d1b9998c-b4e9-42ec-914a-15cc3af7c71e)


# iv)Access rows and columns
```
import random
import cv2
image=cv2.imread('cat.jpg',1)
image=cv2.resize(image,(400,400))
for i in range (150,200):
    for j in range(image.shape[1]):
        image[i][j]=[random.randint(0,255),
                     random.randint(0,255),
                     random.randint(0,255)] 
cv2.imshow('part image',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
# OUTPUT:
![Screenshot 2024-02-27 210714](https://github.com/Vaishnavi-saravanan/COLOR_CONVERSIONS_OF-IMAGE/assets/118541897/eb1df922-6ebd-4e63-9df5-7ab5fb64f1bc)


# v)Cut and paste portion of image
```
import cv2
image=cv2.imread('cat.jpg',1)
image=cv2.resize(image,(400,400))
tag =image[150:200,110:160]
image[110:160,150:200] = tag
cv2.imshow('partimage1',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
# OUTPUT:
![Screenshot 2024-02-27 212226](https://github.com/Vaishnavi-saravanan/COLOR_CONVERSIONS_OF-IMAGE/assets/118541897/59daba50-eb0c-4feb-bd7e-476a418a7429)


# vi) BGR and RGB to HSV and GRAY
```
import cv2
img = cv2.imread('cat.jpg',1)
img = cv2.resize(img,(300,200))
cv2.imshow('Original Image',img)

hsv1 = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('BGR2HSV',hsv1)

hsv2 = cv2.cvtColor(img,cv2.COLOR_RGB2HSV)
cv2.imshow('RGB2HSV',hsv2)

gray1 = cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
cv2.imshow('BGR2GRAY',gray1)

gray2 = cv2.cvtColor(img,cv2.COLOR_RGB2GRAY)
cv2.imshow('RGB2GRAY',gray2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
# OUTPUT:
![Screenshot 2024-02-27 212409](https://github.com/Vaishnavi-saravanan/COLOR_CONVERSIONS_OF-IMAGE/assets/118541897/0bc2cd35-b5dd-4465-ba4a-4b31259037a7)

# vii) HSV to RGB and BGR
```
import cv2
img = cv2.imread('cat.jpg')
img = cv2.resize(img(300,200))

img = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('Original HSV Image',img)

RGB = cv2.cvtColor(img,cv2.COLOR_HSV2RGB)
cv2.imshow('2HSV2BGR',RGB)

BGR = cv2.cvtColor(img,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',BGR)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
# OUTPUT:
![Screenshot 2024-02-27 212457](https://github.com/Vaishnavi-saravanan/COLOR_CONVERSIONS_OF-IMAGE/assets/118541897/ce46b350-04cf-420c-84e5-19b657eebdfe)


# viii) RGB and BGR to YCrCb
```
import cv2
img = cv2.imread('cat.jpg')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
# OUTPUT:

![Screenshot 2024-02-27 212637](https://github.com/Vaishnavi-saravanan/COLOR_CONVERSIONS_OF-IMAGE/assets/118541897/e7cd5f4f-f49d-4240-ba68-765323405c94)

# ix) Split and merge RGB Image
```
import cv2
img = cv2.imread('cat.jpg',1)
img = cv2.resize(img,(300,200))

R = img[:,:,2]
G = img[:,:,1]
B = img[:,:,0]

cv2.imshow('R-Channel',R)
cv2.imshow('G-Channel',G)
cv2.imshow('B-Channel',B)

merged = cv2.merge((B,G,R))
cv2.imshow('Merged RGB image',merged)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
# OUTPUT:
![Screenshot 2024-02-27 212737](https://github.com/Vaishnavi-saravanan/COLOR_CONVERSIONS_OF-IMAGE/assets/118541897/a446b119-30dd-4326-942f-09531bcb3f3e)


# x) Split and merge HSV Image
```
import cv2
img = cv2.imread("cat.jpg",1)
img = cv2.resize(img,(300,200))
img=cv2.cvtColor(img,cv2.COLOR_RGB2HSV)

H,S,V=cv2.split(img)

cv2.imshow('Hue',H)
cv2.imshow('Saturation',S)
cv2.imshow('Value',V)

merged = cv2.merge((H,S,V))
cv2.imshow('Merged',merged)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
# OUTPUT:
![Screenshot 2024-02-27 212825](https://github.com/Vaishnavi-saravanan/COLOR_CONVERSIONS_OF-IMAGE/assets/118541897/5a80493a-b669-4b08-a91d-ab895eed45b0)

# Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.
