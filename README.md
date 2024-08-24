# COLOR_CONVERSIONS_OF-IMAGE
## AIM:
To write a python program using OpenCV to do the following image manipulations.

## Software Required:
Anaconda - Python 3.7
## Algorithm:
```
1. Read and Display an Image:

Load an image from your local directory and display it.

2. Draw Shapes and Add Text:

Draw a line from the top-left to the bottom-right of the image.

Draw a circle at the center of the image.

Draw a rectangle around a specific region of interest in the image.

Add the text "OpenCV Drawing" at the top-left corner of the image.

3. Image Color Conversion:

Convert the image from RGB to HSV and display it.

Convert the image from RGB to GRAY and display it.

Convert the image from RGB to YCrCb and display it.

Convert the HSV image back to RGB and display it.

4. Access and Manipulate Image Pixels:

Resize the original image to half its size and display it.

6. Image Cropping:

Crop a region of interest (ROI) from the image (e.g., a 100x100 pixel area starting at (50, 50)) and display it.

7. Image Flipping:

Flip the original image horizontally and display it.

Flip the original image vertically and display it.

8. Write and Save the Modified Image:

Save the final modified image to your local directory.
```

# Program:
```
Developed By: V Sai Sruthi
Register Number: 212223100061
```


### 1.) Read and display the image

```Python
import cv2
image=cv2.imread('Nature.jpg',1)
cv2.imshow('Image Window', image)
cv2.waitKey(0)
cv2.destroyAllWindows()
``` 
 

### OUTPUT:

![image](https://github.com/user-attachments/assets/6a7a0564-ab27-4bb4-80f3-22c108c18e2c)

 

### 2.) Draw Shapes and Add Text:
i)Draw a line from the top-left to the bottom-right of the image.

```Python
import cv2
img = cv2.imread("Nature.JPG")
res = cv2.line(img, (0, 0), (599, 799), (200, 100, 205), 10)
cv2.imshow('Image Window', res)
cv2.waitKey(0)
cv2.destroyAllWindows()


```


### OUTPUT:


![image](https://github.com/user-attachments/assets/86dee302-a785-4544-b8aa-e4ec3fdf5571)



 
### ii)Draw a circle at the center of the image.
```Python
import cv2

# Load the image
img = cv2.imread("Nature.JPG")

# Get the dimensions of the image
height, width, _ = img.shape

# Calculate the center of the image
center_coordinates = (width // 2, height // 2)

# Draw a circle at the center of the image
res = cv2.circle(img, center_coordinates, 150, (255, 0, 0), 10)

# Display the image with the circle
cv2.imshow('Image Window', res)
cv2.waitKey(0)
cv2.destroyAllWindows()

```


### OUTPUT:

![image](https://github.com/user-attachments/assets/7fd7b197-8fdf-4d0f-a345-20d1b322fce8)


      
### iii)Draw a rectangle around a specific region of interest in the image.
```Python
import cv2

img = cv2.imread("Nature.JPG")
start=(0,0)
stop=(409,529)
color=(100,255,100)
thickness=10
res_img=cv2.rectangle(img,start,stop,color,thickness)
# Display the HSV image
cv2.imshow('Image Window', res_img)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
 

### OUTPUT:


![image](https://github.com/user-attachments/assets/64b1e5b8-bc68-4a5a-8f92-3619d9ae807b)

      
### iv)Add the text "OpenCV Drawing" at the top-left corner of the image.

 ```Python
import cv2

# Load the image
img = cv2.imread("Nature.JPG")

# Define the text to be added and its position
text = "OPENCV DRAWING"
position = (50, 50)  # Positioning the text at the top-left corner

# Set the font, scale, color, and thickness of the text
font = cv2.FONT_HERSHEY_SIMPLEX
font_scale = 1
color = (255, 255, 255)  # White color
thickness = 2

# Add the text to the image
res = cv2.putText(img, text, position, font, font_scale, color, thickness, cv2.LINE_AA)

# Display the image with the text
cv2.imshow('Image Window', res)
cv2.waitKey(0)
cv2.destroyAllWindows()

```

    
### OUTPUT:

![image](https://github.com/user-attachments/assets/b6b5a4ca-7d57-40fa-9a64-ae4fb490b61b)



### 3.)Image Color Conversion:
i)Convert the image from RGB to HSV and display it.
```Python
import cv2
img = cv2.imread('Nature.jpg',1)
img = cv2.resize(img,(300,200))
cv2.imshow('Original Image',img)
hsv2 = cv2.cvtColor(img,cv2.COLOR_RGB2HSV)
cv2.imshow('RGB2HSV',hsv2)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

### OUTPUT:

![image](https://github.com/user-attachments/assets/d43da3bc-0aa4-4d35-9af0-cf12e4ca8e20)

#### ii.)Convert the image from RGB to GRAY and display it.
```Python
import cv2
img = cv2.imread('Nature.jpg',1)
img = cv2.resize(img,(300,200))
cv2.imshow('Original Image',img)
gray2 = cv2.cvtColor(img,cv2.COLOR_RGB2GRAY)
cv2.imshow('RGB2GRAY',gray2)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

### Output:

![image](https://github.com/user-attachments/assets/3f5aadb1-c0a2-4262-87ff-cbb90da3ef1a)

#### iii.)Convert the image from RGB to YCrCb and display it.
```Python
import cv2
img = cv2.imread('Nature.jpg',1)
img = cv2.resize(img,(300,200))
cv2.imshow('Original Image',img)
YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)
cv2.waitKey(0)
cv2.destroyAllWindows()

```
### Output:

![image](https://github.com/user-attachments/assets/35d703be-2f53-421d-b684-34ac092e486a)



#### iv.)Convert the HSV image back to RGB and display it.
```Python
import cv2
img = cv2.imread('Nature.jpg',1)
img = cv2.resize(img,(300,200))
cv2.imshow('Original Image',img)
BGR = cv2.cvtColor(img,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',BGR)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### Output:

![image](https://github.com/user-attachments/assets/54a90a9a-14b0-4bd0-b3a2-7510b99bebf2)


## 4. Access and Manipulate Image Pixels:
```Python
import cv2

# Load and resize the image
img = cv2.imread('Nature.jpg', 1)
img = cv2.resize(img, (300, 200))

# Show the original image
cv2.imshow('Original Image', img)

# 1. Access and print the value of the pixel at coordinates (100, 100)
pixel_value = img[100, 100]
print(f"Pixel value at (100, 100): {pixel_value}")

# 2. Modify the color of the pixel at (199, 199) to white
img[199, 199] = [255, 255, 255]  # Setting the pixel value to white (BGR)

# Display the modified image
cv2.imshow('Modified Image', img)

# Wait for a key press and close the windows
cv2.waitKey(0)
cv2.destroyAllWindows()

```
### Output:

![image](https://github.com/user-attachments/assets/f0c9a034-e441-4e6d-8a46-f15cc94b0fbd)



![image](https://github.com/user-attachments/assets/fe8bf36b-3d98-426c-838a-e7c8eb2f8956)


## 5. Image Resizing:
```Python
width=600
height=800
half_width=300
half_height=400
resized_img = cv2.resize(image, (300, 400))
cv2.imshow('Original',image)
cv2.imshow('resized',resized_img)
cv2.waitKey(0)
cv2.destroyAllWindows()

```
### Output:

![image](https://github.com/user-attachments/assets/4da275ad-195c-4819-87a7-d87f45895d2e)


## 6.Image Cropping:
```Python
import cv2

# Load the image
image1=cv2.imread('Nature.jpg',1)

# Define the starting point and size of the ROI
x, y = 50, 50
width, height = 100, 100

# Crop the ROI
roi = image1[y:y + height, x:x + width]

# Display the cropped ROI
cv2.imshow('Cropped Image', roi)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### Output:

![image](https://github.com/user-attachments/assets/dec33c34-40e2-4f21-9678-685c396c17d4)



## 7.Image Flipping:
i.)Flip the original image horizontally and display it.
```Python

import cv2
img = cv2.imread("Nature.JPG")
img = cv2.resize(img,(300,200))
res=cv2.rotate(img,cv2.ROTATE_180)
cv2.imshow('Original',img)
cv2.imshow('Image Window', res)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### Output:

![image](https://github.com/user-attachments/assets/cc37f630-8467-4301-982e-75185932e749)


#### ii.)Flip the original image vertically and display it.

```Python
import cv2

img = cv2.imread("Nature.JPG")
img = cv2.resize(img,(300,200))
res=cv2.rotate(img,cv2.ROTATE_90_CLOCKWISE)
# Display the HSV image
cv2.imshow('Original',img)
cv2.imshow('Image Window', res)
cv2.waitKey(0)
cv2.destroyAllWindows()

```
### Output:

![image](https://github.com/user-attachments/assets/e68dbc43-1de2-4d8d-ad56-b92f849174dc)

## 8. Write and Save the Modified Image:
```Python
import cv2
img = cv2.imread("Nature.JPG")
img = cv2.resize(img,(300,200))
cv2.imwrite('sunny1.jpg',img)
```
### Output:

![image](https://github.com/user-attachments/assets/000373d1-ee42-4a7d-995f-aaf41788b036)


## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.


