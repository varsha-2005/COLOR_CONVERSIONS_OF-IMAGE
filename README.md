# COLOR_CONVERSIONS_OF-IMAGE
## AIM
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

##### Program:
### Developed By:VARSHA G
### Register Number: 212222230166


## Output:

### i) Read and display the image

```python
    import cv2
    image=cv2.imread('dog.jpg',1)
    image=cv2.resize(image,(300,300))
    cv2.imshow('varsha',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
![Screenshot 2024-04-05 095017](https://github.com/varsha-2005/COLOR_CONVERSIONS_OF-IMAGE/assets/119288183/ed9afa26-bac3-49eb-8d2c-1d15d3d420c1)


![image](https://github.com/22003264/COLOR_CONVERSIONS_OF-IMAGE/assets/119389139/8925c914-2c0c-4787-9833-23590601993a)

### ii)Write the image

```python
    import cv2
    image=cv2.imread('dog.jpg',0)
    cv2.imwrite('demos.jpg',image)
```
![Screenshot 2024-02-15 092418](https://github.com/Leann4468/COLOR_CONVERSIONS_OF-IMAGE/assets/121165979/51d0e6b2-d4df-4788-aad9-b915cec7f607)

### iii)Shape of the Image

```python
    import cv2
    image=cv2.imread('dop.jpg',1)
    print(image.shape)
```
![image](https://github.com/Leann4468/COLOR_CONVERSIONS_OF-IMAGE/assets/121165979/ae32dcb6-54eb-4ce5-8c66-03d25335920a)


### iv)Access rows and columns

```python
import random
    import cv2
    image=cv2.imread('dog.jpg',1)
    image=cv2.resize(image,(500,500))
    for i in range (250,500):
      for j in range(image.shape[1]):
          image[i][j]=[random.randint(0,255),
                       random.randint(0,255),
                       random.randint(0,255)] 
    cv2.imshow('part image',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
![Screenshot 2024-02-15 130641](https://github.com/Leann4468/COLOR_CONVERSIONS_OF-IMAGE/assets/121165979/657e161c-be5b-44d5-8b9e-000a9f5e0b1c)

![image](https://github.com/Leann4468/COLOR_CONVERSIONS_OF-IMAGE/assets/121165979/16bc9ccf-3e76-48c5-be6e-525f33481336)


### v)Cut and paste portion of image

```python
  import cv2
  image=cv2.imread('dog.jpg',1)
  image=cv2.resize(image,(300,300))
  tag =image[150:200,110:160]
  image[110:160,150:200] = tag
  cv2.imshow('image1',image)
  cv2.waitKey(0)
  cv2.destroyAllWindows()
```

![Screenshot 2024-02-15 130948](https://github.com/Leann4468/COLOR_CONVERSIONS_OF-IMAGE/assets/121165979/7ffe4b36-c8d7-4902-a3a1-e9720647682e)

![image](https://github.com/Leann4468/COLOR_CONVERSIONS_OF-IMAGE/assets/121165979/55d4b30d-eb08-41e2-917c-12421d56e475)

### vi) BGR and RGB to HSV and GRAY

```python
import cv2
img = cv2.imread('dog.jpg',1)
img = cv2.resize(img,(200,200))
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

![Screenshot 2024-02-15 131128](https://github.com/Leann4468/COLOR_CONVERSIONS_OF-IMAGE/assets/121165979/a3006cdb-b35a-419c-8f88-a986de2072c4)

![Screenshot 2024-02-15 093233](https://github.com/Leann4468/COLOR_CONVERSIONS_OF-IMAGE/assets/121165979/cc62b399-3a2b-4fdf-8083-4ba55990d25c)


### vii) HSV to RGB and BGR

```python
import cv2
img = cv2.imread('dog.jpg')
img = cv2.resize(img,(200,200))

img = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('Original HSV Image',img)

RGB = cv2.cvtColor(img,cv2.COLOR_HSV2RGB)
cv2.imshow('2HSV2BGR',RGB)

BGR = cv2.cvtColor(img,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',BGR)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
![Screenshot 2024-02-15 131211](https://github.com/Leann4468/COLOR_CONVERSIONS_OF-IMAGE/assets/121165979/88206ce0-702d-4986-aa3c-ad55dc8fc5b5)

![Screenshot 2024-02-15 094233](https://github.com/Leann4468/COLOR_CONVERSIONS_OF-IMAGE/assets/121165979/61f824ad-b53d-47c5-adce-76572eb41d2a)


### viii) RGB and BGR to YCrCb

```python
import cv2
img = cv2.imread('dog.jpg')
img = cv2.resize(img,(200,200))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
![Screenshot 2024-02-15 131312](https://github.com/Leann4468/COLOR_CONVERSIONS_OF-IMAGE/assets/121165979/57380cdc-e99a-480f-82a9-5fa8600afc0a)

![Screenshot 2024-02-15 094514](https://github.com/Leann4468/COLOR_CONVERSIONS_OF-IMAGE/assets/121165979/4d99ec3c-85c2-46cc-874c-b417de42929e)


### ix) Split and merge RGB Image
```python
import cv2
img = cv2.imread('dog.jpg',1)
img = cv2.resize(img,(200,200))

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
![Screenshot 2024-02-15 131359](https://github.com/Leann4468/COLOR_CONVERSIONS_OF-IMAGE/assets/121165979/90f840e4-7d15-435a-8e06-17513b052240)

![Screenshot 2024-02-15 095036](https://github.com/Leann4468/COLOR_CONVERSIONS_OF-IMAGE/assets/121165979/f66751f7-ec00-406d-894a-5d84df99c50f)

### x) Split and merge HSV Image
```python
import cv2
img = cv2.imread("dog.jpg",1)
img = cv2.resize(img,(200,200))
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
![Screenshot 2024-02-15 131434](https://github.com/Leann4468/COLOR_CONVERSIONS_OF-IMAGE/assets/121165979/257b3f94-b302-4733-a559-ffb17387b339)

![Screenshot 2024-02-15 095145](https://github.com/Leann4468/COLOR_CONVERSIONS_OF-IMAGE/assets/121165979/5415b9f6-092d-42fa-a288-30c25c2025c9)


## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.
