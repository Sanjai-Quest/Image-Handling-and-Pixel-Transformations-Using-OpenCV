# Image-Handling-and-Pixel-Transformations-Using-OpenCV 

```

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

## Program Developed By:
- **Name:** [Your Name Here]  
- **Register Number:** [Your Register Number Here]

  ### Ex. No. 01

#### 1. Read the image ('Eagle_in_Flight.jpg') using OpenCV imread() as a grayscale image.
```python
img = cv2.imread('Eagle_in_Flight.jpg', 0)
```

#### 2. Print the image width, height & Channel.
```python
print("Height:", img.shape[0])
print("Width:", img.shape[1])
print("Channels:", 1)
```

#### 3. Display the image using matplotlib imshow().
```python
plt.imshow(img, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
plt.show()
```

#### 4. Save the image as a PNG file using OpenCV imwrite().
```python
cv2.imwrite('eagle.png', img)
```

#### 5. Read the saved image above as a color image using cv2.cvtColor().
```python
img_color = cv2.cvtColor(img, cv2.COLOR_GRAY2BGR)
```

#### 6. Display the Colour image using matplotlib imshow() & Print the image width, height & channel.
```python
plt.imshow(cv2.cvtColor(img_color, cv2.COLOR_BGR2RGB))
plt.title("Color Image")
plt.axis('off')
plt.show()

print(img_color.shape)
```

#### 7. Crop the image to extract any specific (Eagle alone) object from the image.
```python
crop = img_color[100:400, 200:500]
plt.imshow(cv2.cvtColor(crop, cv2.COLOR_BGR2RGB))
plt.show()
```

#### 8. Resize the image up by a factor of 2x.
```python
resized = cv2.resize(crop, None, fx=2, fy=2)
plt.imshow(cv2.cvtColor(resized, cv2.COLOR_BGR2RGB))
plt.show()
```

#### 9. Flip the cropped/resized image horizontally.
```python
flipped = cv2.flip(resized, 1)
plt.imshow(cv2.cvtColor(flipped, cv2.COLOR_BGR2RGB))
plt.show()
```

#### 10. Read in the image ('Apollo-11-launch.jpg').
```python
apollo = cv2.imread('Apollo-11-launch.jpg')
```

#### 11. Add the following text to the dark area at the bottom of the image (centered on the image):
```python
text = 'Apollo 11 Saturn V Launch, July 16, 1969'
font_face = cv2.FONT_HERSHEY_PLAIN
cv2.putText(apollo, 
            'Apollo 11 Saturn V Launch, July 16, 1969',
            (50, 500),
            cv2.FONT_HERSHEY_PLAIN,
            2,
            (255, 255, 255),
            2)
```

#### 12. Draw a magenta rectangle that encompasses the launch tower and the rocket.
```python
rect_color = magenta
cv2.rectangle(apollo, (200, 100), (400, 600), (255, 0, 255), 3)
```

#### 13. Display the final annotated image.
```python
plt.imshow(cv2.cvtColor(apollo, cv2.COLOR_BGR2RGB))
plt.axis('off')
plt.show()
```

#### 14. Read the image ('Boy.jpg').
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('Boy.jpg')
img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
```

#### 15. Adjust the brightness of the image.
```python
matrix = np.ones(img.shape, dtype="uint8") * 50
```

#### 16. Create brighter and darker images.
```python
img_brighter = cv2.add(img, matrix)
img_darker = cv2.subtract(img, matrix)
```

#### 17. Display the images (Original Image, Darker Image, Brighter Image).
```python
plt.figure(figsize=(10,5))

plt.subplot(1,3,1)
plt.imshow(img)
plt.title("Original")
plt.axis('off')

plt.subplot(1,3,2)
plt.imshow(img_darker)
plt.title("Darker")
plt.axis('off')

plt.subplot(1,3,3)
plt.imshow(img_brighter)
plt.title("Brighter")
plt.axis('off')

plt.show()
```

#### 18. Modify the image contrast.
```python
img_higher1 = cv2.convertScaleAbs(img, alpha=1.1, beta=0)
img_higher2 = cv2.convertScaleAbs(img, alpha=1.2, beta=0)
img_lower = cv2.convertScaleAbs(img, alpha=0.8, beta=0)
```

#### 19. Display the images (Original, Lower Contrast, Higher Contrast).
```python
plt.figure(figsize=(10,5))

plt.subplot(1,4,1)
plt.imshow(img)
plt.title("Original")
plt.axis('off')

plt.subplot(1,4,2)
plt.imshow(img_lower)
plt.title("Lower Contrast")
plt.axis('off')

plt.subplot(1,4,3)
plt.imshow(img_higher1)
plt.title("Higher 1.1")
plt.axis('off')

plt.subplot(1,4,4)
plt.imshow(img_higher2)
plt.title("Higher 1.2")
plt.axis('off')

plt.show()
```

#### 20. Split the image (boy.jpg) into the B,G,R components & Display the channels.
```python
img_bgr = cv2.imread('Boy.jpg')

b, g, r = cv2.split(img_bgr)

plt.figure(figsize=(10,5))

plt.subplot(1,3,1)
plt.imshow(b, cmap='gray')
plt.title("Blue")

plt.subplot(1,3,2)
plt.imshow(g, cmap='gray')
plt.title("Green")

plt.subplot(1,3,3)
plt.imshow(r, cmap='gray')
plt.title("Red")

plt.show()
```

#### 21. Merged the R, G, B , displays along with the original image
```python
merged_bgr = cv2.merge((b, g, r))
merged_rgb = cv2.cvtColor(merged_bgr, cv2.COLOR_BGR2RGB)

plt.figure(figsize=(8,4))

plt.subplot(1,2,1)
plt.imshow(img)
plt.title("Original")
plt.axis('off')

plt.subplot(1,2,2)
plt.imshow(merged_rgb)
plt.title("Merged")
plt.axis('off')

plt.show()
```

#### 22. Split the image into the H, S, V components & Display the channels.
```python
hsv = cv2.cvtColor(img_bgr, cv2.COLOR_BGR2HSV)
h, s, v = cv2.split(hsv)

plt.figure(figsize=(10,5))

plt.subplot(1,3,1)
plt.imshow(h, cmap='gray')
plt.title("Hue")

plt.subplot(1,3,2)
plt.imshow(s, cmap='gray')
plt.title("Saturation")

plt.subplot(1,3,3)
plt.imshow(v, cmap='gray')
plt.title("Value")

plt.show()
```
#### 23. Merged the H, S, V, displays along with original image.
```python
merged_hsv = cv2.merge((h, s, v))
rgb_from_hsv = cv2.cvtColor(merged_hsv, cv2.COLOR_HSV2RGB)

plt.figure(figsize=(8,4))

plt.subplot(1,2,1)
plt.imshow(img)
plt.title("Original")
plt.axis('off')

plt.subplot(1,2,2)
plt.imshow(rgb_from_hsv)
plt.title("HSV Merged")
plt.axis('off')

plt.show()
```

## Output:
- **i)** Read and Display an Image.  
- **ii)** Adjust Image Brightness.  
- **iii)** Modify Image Contrast.  
- **iv)** Generate Third Image Using Bitwise Operations.

## Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.

