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
# YOUR CODE HERE
```

#### 15. Adjust the brightness of the image.
```python
# Create a matrix of ones (with data type float64)
# matrix_ones = 
# YOUR CODE HERE
```

#### 16. Create brighter and darker images.
```python
img_brighter = cv2.add(img, matrix)
img_darker = cv2.subtract(img, matrix)
# YOUR CODE HERE
```

#### 17. Display the images (Original Image, Darker Image, Brighter Image).
```python
# YOUR CODE HERE
```

#### 18. Modify the image contrast.
```python
# Create two higher contrast images using the 'scale' option with factors of 1.1 and 1.2 (without overflow fix)
matrix1 = 
matrix2 = 
# img_higher1 = 
# img_higher2 = 
# YOUR CODE HERE
```

#### 19. Display the images (Original, Lower Contrast, Higher Contrast).
```python
# YOUR CODE HERE
```

#### 20. Split the image (boy.jpg) into the B,G,R components & Display the channels.
```python
# YOUR CODE HERE
```

#### 21. Merged the R, G, B , displays along with the original image
```python
# YOUR CODE HERE
```

#### 22. Split the image into the H, S, V components & Display the channels.
```python
# YOUR CODE HERE
```
#### 23. Merged the H, S, V, displays along with original image.
```python
# YOUR CODE HERE
```

## Output:
- **i)** Read and Display an Image.  
- **ii)** Adjust Image Brightness.  
- **iii)** Modify Image Contrast.  
- **iv)** Generate Third Image Using Bitwise Operations.

## Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.

