# EXP-1 Image Handling and Pixel Transformations Using OpenCV

## NAME : MEYYAPPAN T
## REGISTER NUMBER : 212223240086

## AIM
Write a Python program using OpenCV that performs the following tasks:

Read and Display an Image.
Adjust the brightness of an image.
Modify the image contrast.
Generate a third image using bitwise operations.

## Software Required

Anaconda - Python 3.7
Jupyter Notebook (for interactive development and execution)

## Algorithm

### Step 1:
Load an image from your local directory and display it.

### Step 2:
o Draw a line from the top-left to the bottom-right of the image.

o Draw a circle at the center of the image. 

o Draw a rectangle around a specific region of interest in the image. 

o Add the text "OpenCV Drawing" at the top-left corner of the image.

### Step 3:
o Convert the image from RGB to HSV and display it.
    
o Convert the image from RGB to GRAY and display it. 

o Convert the image from RGB to YCrCb and display it. 
    
o Convert the HSV image back to RGB and display it.

### Step 4:
o Access and print the value of the pixel at coordinates (100, 100). 

o Modify the color of the pixel at (200, 200) to white.

### Step 5:
o Resize the original image to half its size and display it. 

### Step 6:
o Crop a region of interest (ROI) from the image (e.g., a 100x100 pixel area starting at (50, 50)) and display it.

### Step 7:
o Crop a region of interest (ROI) from the image (e.g., a 100x100 pixel area starting at (50, 50)) and display it.

o Flip the original image horizontally and display it. 

o Flip the original image vertically and display it.

### Step 8:
o Save the final modified image to your local directory.

## Program

# Experiment 1 - Code
```python
import cv2
import matplotlib.pyplot as plt
```
```python
# Read the image using OpenCV
img = cv2.imread('sekiro.jpeg', cv2.IMREAD_COLOR)
```
```python
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
```
```python
# Display the image using Matplotlib
plt.imshow(img_rgb, cmap='viridis')  # You can change 'viridis' to another cmap or use None for RGB images
plt.title("Original Image")
plt.axis('off')  # Removes axis ticks and labels
plt.show()
```
```python
# Load the image
image = cv2.imread('sekiro.jpeg')
```
```python
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
```
```python
img_rgb.shape
```
```python
# Draw a line from top-left to bottom-right
line_img = cv2.line(img_rgb, (0, 0), (359, 359), (255, 0, 0), 15) # cv2.line(image, start_point, end_point, color, thickness)
```
```python
plt.imshow(line_img, cmap='viridis')  
plt.title("Image with Line")
plt.axis('off')  
plt.show()
```
```python
# Load the image
image = cv2.imread('sekiro.jpeg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
```
```python
img_rgb.shape
```
```python
circle_img = cv2.circle(img_rgb,(180,180),100,(0,0,255),15) # cv2.circle(image, center, radius, color, thickness)
```
```python
plt.imshow(circle_img, cmap='viridis')  
plt.title("Image with Circle")
plt.axis('off')  
plt.show()
```
```python
# Load the image
image = cv2.imread('sekiro.jpeg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
```
```python
img.shape
```
```python
# Draw a rectangle around the Whole image
rectangle_img = cv2.rectangle(img_rgb, (50, 50), (310, 310), (0, 255, 0), 15)  # cv2.rectangle(image, start_point, end_point, color, thickness)
```
```python
plt.imshow(rectangle_img, cmap='viridis')  
plt.title("Image with Rectangle")
plt.axis('off')  
plt.show()
```
```python
# Load the image
image = cv2.imread('sekiro.jpeg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
```
```python
# Add text to the image
text_img = cv2.putText(img_rgb, "Loknaath P", (10, 30), cv2.FONT_HERSHEY_SIMPLEX, 1, (0, 0, 255), 5)  ## cv2.putText(image, text, position, font, font_scale, color, thickness)
```
```python
plt.imshow(text_img, cmap='viridis')  
plt.title("Image with Text")
plt.axis('off')  
plt.show()
```
```python
# Load the image
image = cv2.imread('sekiro.jpeg')
```
```python
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
```
```python
# Original RGB Image
plt.imshow(image_rgb)
plt.title("Original RGB Image")
plt.axis("off")
```
```python
# Convert RGB to HSV
image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)
```
```python
# HSV Image
plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")
```
```python
# Convert RGB to GRAY
image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)
```
```python
# Grayscale Image
plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")
```
```python
# Convert RGB to YCrCb
image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)
```
```python
# YCrCb Image
plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")
```
```python
# Convert HSV back to RGB
image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)
```
```python
plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")
```
```python
# Modify a block of pixels (300x300) to white, starting from (200, 200)
image[200:500, 200:500] = [255, 255, 255]  # Rows: 200-499, Columns: 200-499
```
```python
# Convert BGR to RGB for displaying with Matplotlib
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
```
```python
# Display the modified image
plt.imshow(image_rgb)
plt.title("Image with 300x300 White Block")
plt.axis("off")
plt.show()
```
```python
# Load the image
image = cv2.imread('sekiro.png')
```
```python
image.shape
```
```python
# Resize the image to half its size
resized_image = cv2.resize(image, (768 // 2, 600 // 2))  # (new_width, new_height)
```
```python
# Convert BGR to RGB for displaying with Matplotlib
resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)
```
```python
resized_image_rgb.shape
```
```python
# Display the resized image
plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()
```
```python
# Load the image
image = cv2.imread('sekiro.png')
```
```python
image.shape
```
```python
# Crop a 300x300 region starting from (50, 50)
roi = image[50:350, 50:350]  # Rows: 50-349, Columns: 50-349
```
```python
# Convert BGR to RGB for displaying with Matplotlib
roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)
```
```python
# Display the cropped region (ROI)
plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()
```
```python
# Load the image
image = cv2.imread('sekiro.jpeg')
```
```python
# Flip the image horizontally (left-right)
flipped_horizontally = cv2.flip(image, 1)
```
```python
# Convert BGR to RGB for displaying with Matplotlib
flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)
```
```python
# Horizontal flip
plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")
```
```python
# Flip the image vertically (up-down)
flipped_vertically = cv2.flip(image, 0)
```
```python
# Convert BGR to RGB for displaying with Matplotlib
flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)
```
```python
# Vertical flip
plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")
```

## Output
<img width="389" height="411" alt="image" src="https://github.com/user-attachments/assets/c526edd2-7376-4fe6-bf3a-f4858a7f3922" />


<img width="389" height="411" alt="image" src="https://github.com/user-attachments/assets/b72ab1c7-348d-4c66-9d88-c75e8f5a3c04" />


<img width="389" height="411" alt="image" src="https://github.com/user-attachments/assets/2d85111b-2bce-4e61-8ac9-87752fbe7cc9" />

<img width="389" height="411" alt="image" src="https://github.com/user-attachments/assets/36ce7803-7617-484e-862b-13b94ec0caa4" />

<img width="389" height="411" alt="image" src="https://github.com/user-attachments/assets/3bca127a-eedb-4834-97cb-d17893656f0d" />

<img width="389" height="411" alt="image" src="https://github.com/user-attachments/assets/a3f68cc9-784a-407d-be9c-f62bcdda30d8" />

<img width="389" height="411" alt="image" src="https://github.com/user-attachments/assets/c399e302-9264-4763-84be-ce8fa293a34f" />

<img width="389" height="411" alt="image" src="https://github.com/user-attachments/assets/a35811e2-e66e-4b2f-be52-a913ec92e1dd" />

<img width="389" height="411" alt="image" src="https://github.com/user-attachments/assets/41083363-15de-4c2c-b57e-16eeee42e69d" />

<img width="389" height="411" alt="image" src="https://github.com/user-attachments/assets/9befe17d-d826-4d01-9a34-cfb92b197984" />

<img width="389" height="411" alt="image" src="https://github.com/user-attachments/assets/1105bfc7-91ab-486b-9aa3-fb25a55e9819" />

<img width="389" height="411" alt="image" src="https://github.com/user-attachments/assets/f0f01a26-e634-4262-9e35-d6bad3b76b62" />


<img width="389" height="411" alt="image" src="https://github.com/user-attachments/assets/f83e1366-3a01-48ae-918b-555db0fe8d04" />


<img width="389" height="411" alt="image" src="https://github.com/user-attachments/assets/7561df43-ccbd-4605-ba20-1de9232b76f6" />

<img width="389" height="411" alt="image" src="https://github.com/user-attachments/assets/5676fbc4-71fe-4b53-bb0f-a20c0b0e1d22" />

## Result 

Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.
