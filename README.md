# COLOR_CONVERSIONS_OF-IMAGE
## AIM:
To write a python program using OpenCV to do the following image manipulations.

i) Read, display, and write an image.

ii) Access the rows and columns in an image.

iii) Cut and paste a small portion of the image.

iv)To perform the color conversion between RGB, BGR, HSV, and YCbCr color models.


## Software Required:
Anaconda - Python 3.7
## Algorithm:
### Step1:
Choose an image and save it as a filename.jpg ,
### Step2:
Use imread(filename, flags) to read the file.
### Step3:
Use imshow(window_name, image) to display the image.
### Step4: 
Use imwrite(filename, image) to write the image.
### Step5:
End the program and close the output image windows.
### Step6: 
Convert BGR and RGB to HSV and GRAY
### Step7:
Convert HSV to RGB and BGR
### Step8:
Convert RGB and BGR to YCrCb
### Step9:
Split and Merge RGB Image
### Step10:
Split and merge HSV Image

## Program:

Developed By: Varsha.G
Register Number: 212222230166


### i) Read and display the image
```
    import cv2
    image=cv2.imread('car.jpeg',1)
    image=cv2.resize(image,(400,300))
    cv2.imshow('Adithya',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
 ```

### OUTPUT:

![image](https://github.com/MavillaPranathi/COLOR_CONVERSIONS_OF-IMAGE/assets/118343610/f801b63d-a080-4806-81eb-acf841b582a6)

### ii)Write the image
```
    image=cv2.imread('car.jpeg',0)
    cv2.imwrite('d.jpeg',image)
```


### OUTPUT:

![output02](https://github.com/Adithya-Siddam/COLOR_CONVERSIONS_OF-IMAGE/assets/93427248/214866fe-0f51-4503-be8f-d70177e8f1d0)




### iii)Shape of the Image
```
    import cv2
    image=cv2.imread('car.jpeg',1)
    print(image.shape)
```
 

### OUTPUT:
![output03](https://github.com/Adithya-Siddam/COLOR_CONVERSIONS_OF-IMAGE/assets/93427248/e486b9bb-36ca-4063-8acc-9fa72353fa86)

      
### iv)Access rows and columns
```
    import random
    import cv2
    image=cv2.imread('car.jpeg',1)
    image=cv2.resize(image,(400,400))
    for i in range (150,200):
      for j in range(image.shape[1]):
          image[i][j]=[random.randint(0,255),
                       random.randint(0,255),
                       random.randint(0,255)] 
    cv2.imshow('car part image',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
 
### OUTPUT:

![output04](https://github.com/Adithya-Siddam/COLOR_CONVERSIONS_OF-IMAGE/assets/93427248/6993eb8c-8b01-4935-9a3a-5c64b4377762)


      
### v)Cut and paste portion of image

 ```
   import cv2
   image=cv2.imread('car.jpeg',1)
   image=cv2.resize(image,(400,400))
   tag =image[130:200,110:190]
   image[110:180,120:200] = tag
   cv2.imshow('cut and paste',image)
   cv2.waitKey(0)
   cv2.destroyAllWindows()

```
### OUTPUT:
![output05](https://github.com/Adithya-Siddam/COLOR_CONVERSIONS_OF-IMAGE/assets/93427248/492887c4-d0f9-49e8-b46b-0c387f3e3c4d)


### vi) BGR and RGB to HSV and GRAY
```
import cv2
img = cv2.imread('car.jpeg',1)
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

### OUTPUT:
![output06](https://github.com/Adithya-Siddam/COLOR_CONVERSIONS_OF-IMAGE/assets/93427248/7fe1630a-969f-4877-85e0-4b9fe41a0224)
![output07](https://github.com/Adithya-Siddam/COLOR_CONVERSIONS_OF-IMAGE/assets/93427248/80c1512c-d39d-485f-b8de-b2ae8e288cac)




### vii) HSV to RGB and BGR
```
import cv2
img = cv2.imread('car.jpeg')
img = cv2.resize(img,(300,200))
img = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('Original HSV Image',img)
RGB = cv2.cvtColor(img,cv2.COLOR_HSV2RGB)
cv2.imshow('2HSV2BGR',RGB)
BGR = cv2.cvtColor(img,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',BGR)
cv2.waitKey(0)
cv2.destroyAllWindows()

```
### OUTPUT:
![output08](https://github.com/Adithya-Siddam/COLOR_CONVERSIONS_OF-IMAGE/assets/93427248/4869ed16-d1e1-43a5-824c-04b52b806ee9)



### viii) RGB and BGR to YCrCb
```
import cv2
img = cv2.imread('car.jpeg')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)
YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)
YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

### OUTPUT:
![output09](https://github.com/Adithya-Siddam/COLOR_CONVERSIONS_OF-IMAGE/assets/93427248/eae7abf4-daf0-4b9f-9ae0-10b63c6a2c37)




### ix) Split and merge RGB Image
```
import cv2
img = cv2.imread('car.jpeg',1)
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

### OUTPUT:
![output10](https://github.com/Adithya-Siddam/COLOR_CONVERSIONS_OF-IMAGE/assets/93427248/6cb9058d-0380-4f50-9de4-7f0ed27626f9)




### x) Split and merge HSV Image
```
import cv2
img = cv2.imread("car.jpeg",1)
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

### OUTPUT:

![output11](https://github.com/Adithya-Siddam/COLOR_CONVERSIONS_OF-IMAGE/assets/93427248/9f427016-dd6b-4430-961a-3311d56455e7)


## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.
