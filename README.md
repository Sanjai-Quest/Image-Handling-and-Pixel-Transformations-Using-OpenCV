# Image-Handling-and-Pixel-Transformations-Using-OpenCV 

```
Program Developed By
NAME: SANJAI L
REGISTER NUMBER: 212223230184

```

## AIM:
Write a Python program using OpenCV that performs the following tasks:

1) Read and Display an Image.  
2) Adjust the brightness of an image.  
3) Modify the image contrast.  
4) Generate a third image using bitwise operations.

## Software Required:
- Anaconda - Python 3.7
- Jupyter Notebook (for interactive development and execution)

## Algorithm:
### Step 1:
Load an image from your local directory and display it.

### Step 2:
Create a matrix of ones (with data type float64) to adjust brightness.

### Step 3:
Create brighter and darker images by adding and subtracting the matrix from the original image.  
Display the original, brighter, and darker images.

### Step 4:
Modify the image contrast by creating two higher contrast images using scaling factors of 1.1 and 1.2 (without overflow fix).  
Display the original, lower contrast, and higher contrast images.

### Step 5:
Split the image (boy.jpg) into B, G, R components and display the channels

### Ex. No. 01
## PROGRAM
# Step 1: Read and Display Image
```python
import cv2
import matplotlib.pyplot as plt

img = cv2.imread('Qno.1.jpg', cv2.IMREAD_COLOR)

img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

plt.imshow(img_rgb)
plt.title("Original Image")
plt.axis('off')
plt.show()
```
# Step 2: Draw a Line
```python
line_img = cv2.line(img_rgb,(0,0),(768,600),(255,0,0),2)

plt.imshow(line_img)
plt.title("Image with Line")
plt.axis('off')
plt.show()
```

# Step 3: Draw a Circle
```python
circle_img = cv2.circle(img_rgb,(400,300),150,(255,0,0),10)

plt.imshow(circle_img)
plt.title("Image with Circle")
plt.axis('off')
plt.show()
```

# Step 4: Draw a Rectangle

```python
rectangle_img = cv2.rectangle(
img_rgb,(0,0),(768,600),(0,0,255),10
)

plt.imshow(rectangle_img)
plt.title("Image with Rectangle")
plt.axis('off')
plt.show()
```

# Step 5: Add Text

```python
text_img = cv2.putText(
img_rgb,
"OpenCV Drawing",
(10,30),
cv2.FONT_HERSHEY_SIMPLEX,
1,
(255,255,255),
10
)

plt.imshow(text_img)
plt.title("Image with Text")
plt.axis('off')
plt.show()
```
# Step 6: Convert RGB to HSV
```python
image_hsv = cv2.cvtColor(
img_rgb,
cv2.COLOR_RGB2HSV
)

plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis('off')
plt.show()
```

# Step 7: Convert RGB to Gray
```python
image_gray = cv2.cvtColor(
img_rgb,
cv2.COLOR_RGB2GRAY
)

plt.imshow(image_gray,cmap='gray')
plt.title("Gray Image")
plt.axis('off')
plt.show()
```
# Step 8: Convert RGB to YCrCb
```python
image_ycrcb = cv2.cvtColor(
img_rgb,
cv2.COLOR_RGB2YCrCb
)

plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis('off')
plt.show()
```

# Step 9: Convert HSV back to RGB
```python
image_hsv_to_rgb = cv2.cvtColor(
image_hsv,
cv2.COLOR_HSV2RGB
)
```
# Step 10: Modify Pixel Block
```python
img[200:500,200:500]=[255,255,255]

plt.imshow(cv2.cvtColor(
img,
cv2.COLOR_BGR2RGB
))
plt.show()
```

# Step 11: Resize Image
```python
resized_image=cv2.resize(
img,
(768//2,600//2)
)

plt.imshow(
cv2.cvtColor(
resized_image,
cv2.COLOR_BGR2RGB
)
)
plt.show()
```

# Step 12: Crop ROI
```python
roi=img[50:350,50:350]

plt.imshow(
cv2.cvtColor(
roi,
cv2.COLOR_BGR2RGB
)
)
plt.show()
```

# Step 13: Flip Horizontally
```python
flipped_horizontally=cv2.flip(img,1)

plt.imshow(
cv2.cvtColor(
flipped_horizontally,
cv2.COLOR_BGR2RGB
)
)
plt.show()
```

# Step 14: Flip Vertically
```python
flipped_vertically=cv2.flip(img,0)

plt.imshow(
cv2.cvtColor(
flipped_vertically,
cv2.COLOR_BGR2RGB
)
)
plt.show()
```
# Step 15: Save Final Image
```python
cv2.imwrite(
"final_output.jpg",
flipped_horizontally
)
```

# Output:

# Original Image:
<img width="596" height="499" alt="image" src="https://github.com/user-attachments/assets/11ad6b4f-e636-4940-9728-06bd7a5eaea1" />

# Image with Line:
<img width="595" height="488" alt="image" src="https://github.com/user-attachments/assets/86ad09db-0233-4cea-b5e5-437b2c3e4a0f" />

# Image with Circle:
<img width="589" height="502" alt="image" src="https://github.com/user-attachments/assets/61b85a02-031b-4799-bc36-3c0c4657eabb" />

# Image with Rectangle:
<img width="597" height="491" alt="image" src="https://github.com/user-attachments/assets/57e8d6ef-ce66-4f45-894c-9b9d1e6f78b8" />

# Image With Text:
<img width="591" height="496" alt="image" src="https://github.com/user-attachments/assets/7c552199-b733-4fdd-8607-de08c77b4eff" />

# Original RGB Image:
<img width="589" height="495" alt="image" src="https://github.com/user-attachments/assets/cd64df75-14c5-41ad-8568-331a529e1d9b" />

# HSV Image:
<img width="590" height="491" alt="image" src="https://github.com/user-attachments/assets/3dcdbb22-efe5-4963-b725-b40690903e02" />

# GrayScale Image:
<img width="592" height="493" alt="image" src="https://github.com/user-attachments/assets/a56f9a8c-15bb-4275-ac85-6c9c2e572e8c" />

# YCrCb Image:

<img width="590" height="490" alt="image" src="https://github.com/user-attachments/assets/2c04daa0-450e-4fdd-992e-6c3d5b468ff5" />

# HSV to RGB Image:
<img width="594" height="487" alt="image" src="https://github.com/user-attachments/assets/040b3802-b72a-4878-ac04-294fa4a9f311" />

# Image with 300 x 300 White Block:
<img width="600" height="495" alt="image" src="https://github.com/user-attachments/assets/38783213-a90e-4682-a2a9-760611edc7ba" />

# Resized Image (Half Size):
<img width="584" height="485" alt="image" src="https://github.com/user-attachments/assets/fa5448d8-1d2e-4c19-90e0-642cbaea8f38" />

# Cropped Region of Interest (ROI):
<img width="466" height="494" alt="image" src="https://github.com/user-attachments/assets/5336ffb0-1f5c-4316-b29b-e37fa17cacd6" />

# Flipped Horizontally:
<img width="588" height="489" alt="image" src="https://github.com/user-attachments/assets/b4728e86-3f50-4dbc-97e8-c441cd097cbb" />

# Flipped Vertically:
<img width="584" height="491" alt="image" src="https://github.com/user-attachments/assets/6ee7ee7a-9760-4362-9475-efbb17841aab" />


## Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.

