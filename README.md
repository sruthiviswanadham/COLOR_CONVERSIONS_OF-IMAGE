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
### Developed By: VISWANADHAM VENKATA SAI SRUTHI
### Register Number: 212223100061


## Output:

### i) Read and display the image

```
import cv2
from google.colab.patches import cv2_imshow 

image=cv2.imread('/content/bird.jpg')
image=cv2.resize(image,(400,400))
cv2_imshow(image) 
cv2.waitKey(0)
cv2.destroyAllWindows()
```
Output:

![image](https://github.com/user-attachments/assets/8fbe126b-8fe0-4920-a6c1-db2d3b67362b)

### ii)Write the image
```
image=cv2.imread('/content/bird.jpg',0)
cv2.imwrite("/content/bird.jpg",image)
```
Output:

![IMAGE 2](https://github.com/user-attachments/assets/9dbd57da-f0f2-40c0-b6ae-f0a1947a1d81)

### iii)Shape of the Image
```
import cv2
image=cv2.imread('/content/bird.jpg',1)
print(image.shape)
```
Output:

![IMAGE 3](https://github.com/user-attachments/assets/b666d04e-69e9-426b-b5a7-00ed497d46a6)

### iv)Access rows and columns
```
import random
import cv2
from google.colab.patches import cv2_imshow # Import the correct function for Colab

image=cv2.imread('/content/bird.jpg',1)
image=cv2.resize(image,(400,400))
for i in range (150,200):
  for j in range(image.shape[1]):
      image[i][j]=[random.randint(0,255),
                   random.randint(0,255),
                   random.randint(0,255)] 
cv2_imshow(image) 
cv2.waitKey(0)
cv2.destroyAllWindows()
```
Output:

![image](https://github.com/user-attachments/assets/7a977484-0284-4857-857e-52bbf36df407)

### v)Cut and paste portion of image
```
import cv2
from google.colab.patches import cv2_imshow  # Use cv2_imshow for Colab

image = cv2.imread('/content/bird.jpg', 1)
image = cv2.resize(image, (400, 400))
tag = image[130:200, 110:190]
image[110:180, 120:200] = tag
cv2_imshow(image)  # Replace cv2.imshow with cv2_imshow
cv2.waitKey(0)
cv2.destroyAllWindows()
```
Output:

![image](https://github.com/user-attachments/assets/8b086fdd-baf8-451f-aec4-a68a268445ff)

### vi) BGR and RGB to HSV and GRAY
```
import cv2
from google.colab.patches import cv2_imshow  # Import cv2_imshow

img = cv2.imread('/content/bird.jpg',1)
img = cv2.resize(img,(300,300))
cv2_imshow(img) 
hsv1 = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2_imshow(hsv1)  
hsv2 = cv2.cvtColor(img,cv2.COLOR_RGB2HSV)
cv2_imshow(hsv2)  
gray1 = cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
cv2_imshow(gray1)  
gray2 = cv2.cvtColor(img,cv2.COLOR_RGB2GRAY)
cv2_imshow(gray2) 
cv2.waitKey(0)
cv2.destroyAllWindows()
```
Output:

![image](https://github.com/user-attachments/assets/591450b4-f356-4fbf-b47b-1220c7d19263)
![image](https://github.com/user-attachments/assets/4be0d721-c1e8-4001-9c27-7feeb500ca63)
![image](https://github.com/user-attachments/assets/2842fc9a-a370-4b40-afd8-7cff120af36a)
![image](https://github.com/user-attachments/assets/c0e89efd-9305-440e-8f6a-e58ba8844563)
![image](https://github.com/user-attachments/assets/7e5be429-5b75-4733-8a09-2f56aff4fb3f)

### vii) HSV to RGB and BGR
```
import cv2
from google.colab.patches import cv2_imshow  # Import cv2_imshow for Colab 
img = cv2.imread('/content/bird.jpg')
img = cv2.resize(img,(300,200))
img = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2_imshow(img) # Use cv2_imshow instead of cv2.imshow
RGB = cv2.cvtColor(img,cv2.COLOR_HSV2RGB)
cv2_imshow(RGB) # Use cv2_imshow instead of cv2.imshow
BGR = cv2.cvtColor(img,cv2.COLOR_HSV2BGR)
cv2_imshow(BGR) # Use cv2_imshow instead of cv2.imshow
cv2.waitKey(0)
cv2.destroyAllWindows()
```
Output:

![image](https://github.com/user-attachments/assets/72457059-fb66-413f-ba40-725faf0de877)
![image](https://github.com/user-attachments/assets/876e2bb5-332f-4861-be05-ed295c8f957c)
![image](https://github.com/user-attachments/assets/d44e0717-756d-4790-97f2-51cede8719c2)

### viii) RGB and BGR to YCrCb
```
import cv2
from google.colab.patches import cv2_imshow  # Import the Colab-compatible display function

img = cv2.imread('/content/bird.jpg')
img = cv2.resize(img,(300,300))
cv2_imshow(img)  # Use cv2_imshow to display the image in Colab
YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2_imshow(YCrCb1)  # Use cv2_imshow here as well
YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2_imshow(YCrCb2)  # And here
cv2.waitKey(0)
cv2.destroyAllWindows()
```
Output:

![image](https://github.com/user-attachments/assets/b2f1c8c3-1b27-417a-a890-e52288041a22)
![image](https://github.com/user-attachments/assets/a0a57d3f-413f-4403-bd7f-0e3a0841bdfd)
![image](https://github.com/user-attachments/assets/e82dc687-fcce-44ff-a268-ac7f040d146b)

### ix) Split and merge RGB Image
```
import cv2
from google.colab.patches import cv2_imshow  # Import cv2_imshow for Colab compatibility

img = cv2.imread('/content/bird.jpg',1)
img = cv2.resize(img,(300,200))
R = img[:,:,2]
G = img[:,:,1]
B = img[:,:,0]
cv2_imshow(R)  # Use cv2_imshow instead of cv2.imshow
cv2_imshow(G)  # Use cv2_imshow instead of cv2.imshow
cv2_imshow(B)  # Use cv2_imshow instead of cv2.imshow
merged = cv2.merge((B,G,R))
cv2_imshow(merged)  # Use cv2_imshow instead of cv2.imshow
cv2.waitKey(0)
cv2.destroyAllWindows()
```
Output:

![image](https://github.com/user-attachments/assets/d277b78a-3a48-4ad0-8dae-e6a03a61f014)
![image](https://github.com/user-attachments/assets/3681bdbe-e9eb-4f1e-979a-ab2a11f75aaf)
![image](https://github.com/user-attachments/assets/5e384698-1936-4757-8f21-70e3ac3ca599)
![image](https://github.com/user-attachments/assets/9c16f196-66cd-41be-90d6-fc6b01f8454b)

### x) Split and merge HSV Image
```
import cv2
from google.colab.patches import cv2_imshow  # Import cv2_imshow for Colab compatibility

img = cv2.imread("/content/bird.jpg",1)
img = cv2.resize(img,(300,200))
img=cv2.cvtColor(img,cv2.COLOR_RGB2HSV)
H,S,V=cv2.split(img)
cv2_imshow(H) # Use cv2_imshow instead of cv2.imshow
cv2_imshow(S) # Use cv2_imshow instead of cv2.imshow
cv2_imshow(V) # Use cv2_imshow instead of cv2.imshow
merged = cv2.merge((H,S,V))
cv2_imshow(merged) # Use cv2_imshow instead of cv2.imshow
cv2.waitKey(0)
cv2.destroyAllWindows()
```
Output:

![image](https://github.com/user-attachments/assets/4b12dd5e-3b29-466f-b5e2-e1a7380e74d1)
![image](https://github.com/user-attachments/assets/2e0684db-8f00-46e6-a3f3-1d7a6ed47932)
![image](https://github.com/user-attachments/assets/56784074-350a-447d-9f81-249063f228fb)
![image](https://github.com/user-attachments/assets/88208be9-3c29-4490-a076-32ed0ba17b67)

## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







