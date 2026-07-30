# EXPERIMENT - 1-Image-Handling-and-Pixel-Transformations-Using-OpenCV
# AIM:
Write a Python program using OpenCV that performs the following tasks:

Read and Display an Image.

Adjust the brightness of an image.

Modify the image contrast.

Generate a third image using bitwise operations.

# Software Required:
Anaconda - Python 3.7

Jupyter Notebook (for interactive development and execution)

# Algorithm:
Step 1:

Load an image from your local directory and display it.

Step 2:

Create a matrix of ones (with data type float64) to adjust brightness.

Step 3:

Create brighter and darker images by adding and subtracting the matrix from the original image.

Display the original, brighter, and darker images.

Step 4:

Modify the image contrast by creating two higher contrast images using scaling factors of 1.1 and 1.2 (without overflow fix).

Display the original, lower contrast, and higher contrast images.

Step 5:

Split the image (boy.jpg) into B, G, R components and display the channels

# Program Developed By:
Name: T GOSHANRAJAN
Register Number: 212225040098
Step1: Load an image from your local directory and display it.
```
import cv2
import matplotlib.pyplot as plt
# Read the image using OpenCV
img = cv2.imread('bird.jpg', cv2.IMREAD_COLOR)
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
# Display the image using Matplotlib
plt.imshow(img_rgb, cmap='viridis')  # You can change 'viridis' to another cmap or use None for RGB images
plt.title("Original Image")
plt.axis('off')  # Removes axis ticks and labels
plt.show()
```
Step2:
o Draw a line from the top-left to the bottom-right of the image.

o Draw a circle at the center of the image.

o Draw a rectangle around a specific region of interest in the image.

o Add the text "OpenCV Drawing" at the top-left corner of the image.

Load the image
```
image = cv2.imread('bird.jpg')
```
Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
```
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
```
Draw a line from top-left to bottom-right
```
line_img = cv2.line(img_rgb, (0, 0), (1500, 1000), (255, 0, 0), 2) # cv2.line(image, start_point, end_point, color, thickness)
line_img = cv2.line(img_rgb, (1500, 0), (0, 1000), (255, 0, 0), 2)
# Display the image
plt.imshow(line_img, cmap='viridis')  
plt.title("Image with Line")
plt.axis('off')  
plt.show()
```
Draw a square at the center of the image.
Load the image
```
image = cv2.imread('bird.jpg')
```
Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
```
# Load the image
image = cv2.imread('Q1no. 1.jpg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
(1150, 1500, 3)
square_img = cv2.rectangle(img_rgb, (330, 115), (570, 365), (255,0,0), 3)
plt.imshow(square_img, cmap='viridis')  
plt.title("Image with Square")
plt.axis('off')  
plt.show()
```
Draw a rectangle around the whole image
Load the image
```
image = cv2.imread('bird.jpg')
```
Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
```
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img.shape
```
Draw a rectangle around the Whole image
```
# Draw a rectangle around the Whole image
rectangle_img = cv2.rectangle(img_rgb, (0, 0), (1500, 1200), (0, 0, 255), 10)  # cv2.rectangle(image, start_point, end_point, color, thickness)
plt.imshow(rectangle_img, cmap='viridis')  
plt.title("Image with Rectangle")
plt.axis('off')  
plt.show()
```
Add the text "OpenCV Drawing" at the top-left corner of the image.
Load the image
```
image = cv2.imread('bird.png')
```
Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
```
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
```
Add text to the image
```
text_img = cv2.putText(img_rgb, "CHEETAH", (10, 30), cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 255, 255), 10)  ## cv2.putText(image, text, position, font, font_scale, color, thickness)

plt.imshow(text_img, cmap='viridis')  
plt.title("Image with Text")
plt.axis('off')  
plt.show()
```
Step3:
o Convert the image from RGB to HSV and display it.

o Convert the image from RGB to GRAY and display it.

o Convert the image from RGB to YCrCb and display it.

o Convert the HSV image back to RGB and display it.
Load the image
```
# Load the image
image = cv2.imread('bird.jpg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
```
Original RGB Image
```
plt.imshow(image_rgb)
plt.title("Original RGB Image")
plt.axis("off")
```
Convert RGB to HSV
```
image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)
```
HSV Image
```
plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")
```
Convert RGB to GRAY
```
image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)
```
Grayscale Image
```
plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")
```
Convert RGB to YCrCb
```
image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)
```
YCrCb Image
```
plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")
```
Convert HSV back to RGB
```
image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)
plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")
```
Step4:
o Access and print the value of the pixel at coordinates (100, 100).

o Modify the color of the pixel at (200, 200) to white.

Modify a block of pixels (300x300) to white, starting from (200, 200)
```
image[120:320, 250:400] = [255,255, 255]  # Rows: 200-499, Columns: 200-499
```
Convert BGR to RGB for displaying with Matplotlib
```
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
```
Display the modified image
```
plt.imshow(image_rgb)
plt.title("Image with 300x300 White Block")
plt.axis("off")
plt.show()

image = cv2.imread("bird.jpg")
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

insert_img = cv2.imread("img.jpeg")
```
Resize while keeping aspect ratio
```
insert_img = cv2.resize(insert_img, (150, 200))   # Width=150, Height=200

insert_img = cv2.cvtColor(insert_img, cv2.COLOR_BGR2RGB)
```
Place it
```
image_rgb[120:320, 250:400] = insert_img

plt.imshow(image_rgb)
plt.title("Image with Inserted Image")
plt.axis("off")
plt.show()
```
Step5:
o Resize the original image to half its size and display it.

Load the image
```
image = cv2.imread('bird.jpg') 
image.shape
```
Resize the image to half its size
```
resized_image = cv2.resize(image, (768 // 2, 600 // 2))  # (new_width, new_height)
```
Convert BGR to RGB for displaying with Matplotlib
```
resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)
resized_image_rgb.shape
```
Display the resized image
```
plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()
```
Step6:
o Crop a region of interest (ROI) from the image (e.g., a 100x100 pixel area starting at (50, 50)) and display it.

Load the image
```
image = cv2.imread('bird.jpg')
image.shape
(1150, 1500, 3)
```
Crop a 300x300 region starting from (50, 50)
```
roi = image[50:350, 50:350]  # Rows: 50-349, Columns: 50-349
```
Convert BGR to RGB for displaying with Matplotlib
```
roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)
```
Display the cropped region (ROI)
```
plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()
```
Step7:
o Flip the original image horizontally and display it.

o Flip the original image vertically and display it.

Load the image
```
image = cv2.imread('bird.jpg')
```
Flip the image horizontally (left-right
```
flipped_horizontally = cv2.flip(image, 1)
```
Convert BGR to RGB for displaying with Matplotlib
```
flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)
```
Horizontal flip
```
plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")
(np.float64(-0.5), np.float64(677.5), np.float64(451.5), np.float64(-0.5))
```
Flip the image vertically (up-down)
```
flipped_vertically = cv2.flip(image, 0)
```
Convert BGR to RGB for displaying with Matplotlib
```
flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)
```
Vertical flip
```
plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")
(np.float64(-0.5), np.float64(677.5), np.float64(451.5), np.float64(-0.5))
```
Step8:
o Save the final modified image to your local directory.

# OUTPUT:
<img width="672" height="527" alt="image" src="https://github.com/user-attachments/assets/6c704bf4-8f5f-4a92-a276-465b6cb5adf7" />
<img width="502" height="410" alt="image" src="https://github.com/user-attachments/assets/07bd8671-c6ce-47db-9223-4ae51796ee32" />
<img width="502" height="410" alt="image" src="https://github.com/user-attachments/assets/25e19f37-dca6-4cf5-9a8e-49698cdd4828" />
<img width="502" height="410" alt="image" src="https://github.com/user-attachments/assets/f3371ddb-a2c9-4a83-b02e-aa4d981ecede" />
<img width="502" height="410" alt="image" src="https://github.com/user-attachments/assets/568eb983-b174-4ffd-ae3e-f4c5ce12fcfb" />
<img width="502" height="410" alt="image" src="https://github.com/user-attachments/assets/c077917c-e941-49a5-bcb9-12fb26e2982d" />
<img width="502" height="410" alt="image" src="https://github.com/user-attachments/assets/e104d4dc-a40a-4e7a-88b4-1ef98dc707dc" />
<img width="502" height="410" alt="image" src="https://github.com/user-attachments/assets/6375e375-4b11-4a3e-b5f5-4db4b837b05f" />
<img width="502" height="410" alt="image" src="https://github.com/user-attachments/assets/3d31aa71-85d1-4b59-9067-b1917ead3460" />
<img width="502" height="410" alt="image" src="https://github.com/user-attachments/assets/0c54f25c-daf7-4e93-b8a0-21eaa5fd43f5" />
<img width="502" height="410" alt="image" src="https://github.com/user-attachments/assets/77b8ba89-1690-4f92-bc66-ab3d9c68904b" />
<img width="502" height="410" alt="image" src="https://github.com/user-attachments/assets/d3b123fc-5d93-4faa-9091-a7efe86a7154" />
<img width="502" height="410" alt="image" src="https://github.com/user-attachments/assets/8dfd341e-6c13-4b73-8784-a52ed25cec0b" />
<img width="502" height="410" alt="image" src="https://github.com/user-attachments/assets/9ace3cfc-4297-4a18-8172-77df1b144bb7" />
<img width="502" height="410" alt="image" src="https://github.com/user-attachments/assets/3e61dc80-f169-4708-ae72-e5530ce2f848" />

# Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.




