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
### Step1: Choose an image and save it as a filename.jpg ,
### Step2: Use imread(filename, flags) to read the file.
### Step3: Use imshow(window_name, image) to display the image.
### Step4: Use imwrite(filename, image) to write the image.
### Step5: End the program and close the output image windows.
### Step6: Convert BGR and RGB to HSV and GRAY
### Step7: Convert HSV to RGB and BGR
### Step8: Convert RGB and BGR to YCrCb
### Step9: Split and Merge RGB Image
### Step10: Split and merge HSV Image

## Program:
```
Developed By: M Gautham
Register Number: 212221230027
```
<table>
  <tr>
    <td width=50%>

### i) Read and display the image
```Python
    import cv2
    image=cv2.imread('inter.jpeg',1)
    image=cv2.resize(image,(400,300))
    cv2.imshow('gautham',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
``` 
  </td>
  <td>

### OUTPUT:

![inter](https://github.com/muppirgautham/COLOR_CONVERSIONS_OF-IMAGE/assets/94810884/6991f1f6-1992-4733-bffa-1ddc8d7a919c)


  </td>
  </tr>

   <tr>
    <td width=50%>

### ii)Write the image
```Python
    image=cv2.imread('inter.jpeg',0)
    cv2.imwrite('d.jpeg',image)
```
  </td>
  <td>

### OUTPUT:

![image](https://github.com/muppirgautham/COLOR_CONVERSIONS_OF-IMAGE/assets/94810884/d0b2556a-9baf-434a-ac4a-729fc94cd85c)


  </td>
  </tr>
  <tr>
    <td width=50%>

### iii)Shape of the Image
```Python
    import cv2
    image=cv2.imread('inter.jpeg',1)
    print(image.shape)
```
  </td>
  <td>

### OUTPUT:
![image](https://github.com/muppirgautham/COLOR_CONVERSIONS_OF-IMAGE/assets/94810884/c5a4ba22-7ec0-4682-8ae6-df7096b90209)

  </td>
  </tr>
  <tr>
    <td>
      
### iv)Access rows and columns
```Python
    import random
    import cv2
    image=cv2.imread('inter.jpeg',1)
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
  </td>
  <td width="50%">

### OUTPUT:

![row](https://github.com/muppirgautham/COLOR_CONVERSIONS_OF-IMAGE/assets/94810884/0ce32b74-19de-4715-80ae-ecad4391079e)

  </td>
  </tr>
  <tr>
    <td width=50%>
      
### v)Cut and paste portion of image

 ```Python
   import cv2
   image=cv2.imread('inter.jpeg',1)
   image=cv2.resize(image,(400,400))
   tag =image[130:200,110:190]
   image[110:180,120:200] = tag
   cv2.imshow('cut and paste',image)
   cv2.waitKey(0)
   cv2.destroyAllWindows()
```
  </td>
  <td>
    
### OUTPUT:
![square](https://github.com/muppirgautham/COLOR_CONVERSIONS_OF-IMAGE/assets/94810884/76e799f7-156c-45dd-b0c7-b6d0ec819964)

  </td>
  </tr>
</table>

### vi) BGR and RGB to HSV and GRAY
```Python
import cv2
img = cv2.imread('inter.jpeg',1)
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
![gray](https://github.com/muppirgautham/COLOR_CONVERSIONS_OF-IMAGE/assets/94810884/cd8482dc-b710-4074-870b-6b75c35e0593)




### vii) HSV to RGB and BGR
```Python
import cv2
img = cv2.imread('inter.jpeg')
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
![hsv2](https://github.com/muppirgautham/COLOR_CONVERSIONS_OF-IMAGE/assets/94810884/e97f19c2-c0c5-417b-87bc-214f566113d4)



### viii) RGB and BGR to YCrCb
```Python
import cv2
img = cv2.imread('inter.jpeg')
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
![RGB](https://github.com/muppirgautham/COLOR_CONVERSIONS_OF-IMAGE/assets/94810884/7b9f0d9a-2b91-40fd-bf8c-7c1e5d7a0a86)




### ix) Split and merge RGB Image
```Python
import cv2
img = cv2.imread('inter.jpeg',1)
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
![spilt](https://github.com/muppirgautham/COLOR_CONVERSIONS_OF-IMAGE/assets/94810884/2ee47488-822e-4879-880d-7ec8370cdb7c)




### x) Split and merge HSV Image
```Python
import cv2
img = cv2.imread("inter.jpeg",1)
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

![merge hsv](https://github.com/muppirgautham/COLOR_CONVERSIONS_OF-IMAGE/assets/94810884/016791da-4bb5-4ecb-8dbb-7f5882e00970)


## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







