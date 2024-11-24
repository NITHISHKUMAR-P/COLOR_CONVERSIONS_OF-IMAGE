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
### Developed By: Nithishkumar P
### Register Number: 212221230070
```py
import cv2
import matplotlib.pyplot as plt

#Read and Display the Image
img = cv2.imread('car.jpg',1)
resized_img = cv2.resize(img, None, fx=0.1, fy=0.1)
cv2.imshow('212221230070', resized_img)
cv2.waitKey(0)
cv2.destroyAllWindows()

# Draw shape and add text
resized_img.shape
## Draw line
res = cv2.line(resized_img,(0,0),(1000,535),(100,100,205),10)
cv2.imshow('Image Window', res)
cv2.waitKey(0)
cv2.destroyAllWindows()
## Draw circle
height, width, _ = resized_img.shape
center_coordinates = (width // 2, height // 2)
circle_img = cv2.circle(resized_img, center_coordinates, 50, (0, 255, 0), 5)
cv2.imshow('Image with Circle', circle_img)
cv2.waitKey(0)
cv2.destroyAllWindows()

# Draw a rectangle
rectangle_img = cv2.rectangle(resized_img, (0, 0), (535, 356), (0, 0, 255), 10)
plt.imshow(rectangle_img, cmap='viridis')  
plt.title("Image with Rectangle")
plt.axis('off')  
plt.show()

# Add text
text_img = cv2.putText(resized_img, 'OpenCV Drawing', (10, 30), cv2.FONT_HERSHEY_SIMPLEX, 
                       1, (255, 255, 255), 2, cv2.LINE_AA)
# Display the final image with text
cv2.imshow('Image with Text', text_img)
cv2.waitKey(0)
cv2.destroyAllWindows()

# Image Colour Conversion
rgb2hsv = cv2.cvtColor(resized_img,cv2.COLOR_RGB2HSV)
cv2.imshow('RGB2HSV',rgb2hsv)

rgb2gray = cv2.cvtColor(resized_img,cv2.COLOR_RGB2GRAY)
cv2.imshow('RGB2GRAY',rgb2gray)

rgb2YcrCb = cv2.cvtColor(resized_img,cv2.COLOR_RGB2YCrCb)
cv2.imshow('RGBtoYCrCb',rgb2YcrCb)

hsv2rgb = cv2.cvtColor(rgb2hsv,cv2.COLOR_HSV2RGB)
cv2.imshow('HSVtoRGB',hsv2rgb)

cv2.waitKey(0)
cv2.destroyAllWindows()

# Access and manipulate
# Access and print the pixel value at (100, 100)
pixel_value = resized_img[100,100]
print(f"Pixel value at (100, 100): {pixel_value}")

# Modify the pixel color at (200, 200) to white
resized_img[200:300, 200:300] = [255, 255, 255]

# Convert BGR to RGB for displaying with Matplotlib
image_rgb = cv2.cvtColor(resized_img, cv2.COLOR_BGR2RGB)
plt.imshow(image_rgb)
plt.title("Image with 300x300 White Block")
plt.axis("off")
plt.show()

# Image resizing
resized1_img = cv2.resize(resized_img, None, fx=0.5, fy=0.5)
cv2.imshow('212221230070', resized1_img)
cv2.waitKey(0)
cv2.destroyAllWindows()

# Image cropping
roi = resized_img[120:250, 100:450]

cv2.imshow('Cropped Image', roi)
cv2.waitKey(0)
cv2.destroyAllWindows()

# Image flipping
# Flip the image horizontally
horizontally_flipped = cv2.flip(resized_img, 1)

# Flip the image vertically
vertically_flipped = cv2.flip(resized_img, 0)

cv2.imshow('Horizontally Flipped', horizontally_flipped)
cv2.imshow('Vertically Flipped', vertically_flipped)

cv2.waitKey(0)
cv2.destroyAllWindows()

# write and saveing the image
cv2.imwrite('horizontally_flipped.jpg', horizontally_flipped)
cv2.imwrite('vertically_flipped.jpg', vertically_flipped)
```
## Output:

### i) Read and display the image:
![original_img](https://github.com/user-attachments/assets/2371671a-d8de-4487-8744-85f93146fc31)

### ii)Draw shapes and add text:
#### Line:
![line_img](https://github.com/user-attachments/assets/3921273a-0a1a-4e0d-96f5-5b8ab546f42d)
#### Cirlce:
![circle_img](https://github.com/user-attachments/assets/f3ac748a-828a-4688-922a-c628f10c3ad2)
#### Rectange:
![image](https://github.com/user-attachments/assets/140625e2-9668-464d-bfa7-43a25065f519)

#### Text:
![text_image](https://github.com/user-attachments/assets/90fb0c7a-8335-47e2-9534-3e6396a6c71b)

### iii)Image Color Conversion:
#### RGB to HSV:
![rgb to hsv](https://github.com/user-attachments/assets/af938615-2f91-42f9-8c66-8738edb9d01f)
#### RGB to GRAY:
![rgbtogray](https://github.com/user-attachments/assets/caf3a241-ba4b-415f-9c58-eba3d9ee2af2)
#### RGB to YCrCb:
![rgb to ycrcb](https://github.com/user-attachments/assets/59c2d1be-fd05-4006-9ecd-6be7df862c89)
#### HSV to RGB:
![hsv to rgb](https://github.com/user-attachments/assets/49b5548d-48c5-4730-93c2-e56440211301)

### iv)Access and manipulate image pixels:
#### Pixel coordinate at [100,100]:
![pixel value](https://github.com/user-attachments/assets/8c5c1484-b5fd-452e-8efd-d4104e2a2bc2)
#### Modify color at pixel [200,200] to white:
![image](https://github.com/user-attachments/assets/b5cbc00f-9cbe-4970-b99f-eca45769ba63)


### v)Image Resize:
![resize](https://github.com/user-attachments/assets/8e1ced62-30b5-4cf9-b298-895576f753c1)

### vi)Image Cropping:
![cropped img](https://github.com/user-attachments/assets/58c1b41c-bd8d-4f35-8783-7abd1cc8aa25)

### vii) Write and save modified image:
![image](https://github.com/user-attachments/assets/36bd2cdd-3a49-4e75-ab35-400ac2be251d)

## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







