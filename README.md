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
img = cv2.imread('lion.jpg', cv2.IMREAD_COLOR)
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
image = cv2.imread('lion.jpg')
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
image = cv2.imread('lion.jpg') 

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
image = cv2.imread('lion.jpg') 

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
image = cv2.imread('lion.jpg') 

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
image = cv2.imread('lion.jpg')
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
image = cv2.imread('lion.jpg')
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
image = cv2.imread('lion.jpg')
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
image = cv2.imread('lion.jpg')
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

<img width="389" height="409" alt="download" src="https://github.com/user-attachments/assets/cc649d2e-abe3-4fab-8baf-5a0493f27c45" />

<img width="389" height="409" alt="download" src="https://github.com/user-attachments/assets/de0dcdfa-e78a-4907-b9e8-c77b3199ca20" />

<img width="389" height="409" alt="download" src="https://github.com/user-attachments/assets/b9389e6b-ad15-4c0c-95b5-c17dfc256861" />

<img width="389" height="409" alt="download" src="https://github.com/user-attachments/assets/41765351-4313-4eb7-a750-c327c3bafd17" />

<img width="389" height="409" alt="download" src="https://github.com/user-attachments/assets/9bdf6566-6acc-441d-867a-21dc6d644d13" />

<img width="389" height="409" alt="download" src="https://github.com/user-attachments/assets/5a22d375-71b1-4dac-bbcb-832d74f58912" />

<img width="389" height="409" alt="download" src="https://github.com/user-attachments/assets/e1a89e18-3c54-48aa-9d75-fafd39393a38" />

<img width="389" height="409" alt="download" src="https://github.com/user-attachments/assets/df3e679d-5814-44ad-9b0c-5c33509a7284" />

<img width="389" height="409" alt="download" src="https://github.com/user-attachments/assets/e2d97d07-728b-4b81-8c98-2d4fa1389dbc" />

<img width="389" height="409" alt="download" src="https://github.com/user-attachments/assets/61cce0a6-c726-4798-b160-b73885439130" />

<img width="389" height="409" alt="download" src="https://github.com/user-attachments/assets/3fd13777-e615-4dc9-af1c-3d40dd612f04" />

<img width="493" height="409" alt="download" src="https://github.com/user-attachments/assets/49372280-07a6-40dc-8a42-3c1c87d56f9f" />

<img width="389" height="409" alt="download" src="https://github.com/user-attachments/assets/ff9c32b1-5f2f-4d32-a080-a1ab4a52f5fa" />

<img width="389" height="409" alt="download" src="https://github.com/user-attachments/assets/1e69a920-f17c-46a3-8eff-d5402035a7fa" />

<img width="389" height="409" alt="download" src="https://github.com/user-attachments/assets/da6a3929-079a-4282-aadc-041d68052d8d" />


## Result 

Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.
