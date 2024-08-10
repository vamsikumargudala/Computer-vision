# Image Processing with OpenCV and NumPy in Python

Image processing involves performing operations on images to enhance them or extract useful information. This README outlines tasks involving image creation, cropping, swapping, and combining using Python libraries OpenCV and NumPy.

## Libraries

- **OpenCV**: A library designed for computer vision tasks. It allows for processing images and videos to identify objects, faces, and more.
- **NumPy**: A library for numerical operations in Python, providing support for large, multi-dimensional arrays and matrices.

## Tasks

### Task 4.1: Create an Image Using Python Code

This task involves creating a blank image and drawing shapes on it to create a simple emoji.

#### Code

```python
import numpy as np
import cv2 as cv

# Create a blank image
photo = np.zeros((512, 512, 3), dtype="uint8")
photo[:] = [255, 255, 255]

# Draw an emoji
cv.rectangle(photo, (500, 500), (500, 500), (255, 0, 255), -1)
cv.circle(photo, (256, 256), radius=100, color=[0, 0, 0], thickness=2)
cv.circle(photo, (220, 220), radius=10, color=[0, 0, 0], thickness=-1)
cv.circle(photo, (286, 220), radius=10, color=[0, 0, 0], thickness=-1)
cv.circle(photo, (253, 270), radius=8, color=[0, 0, 0], thickness=-1)
cv.line(photo, (245, 270), (253, 245), [0, 0, 0], 2)
cv.line(photo, (261, 270), (253, 245), [0, 0, 0], 2)
cv.ellipse(photo, (256, 290), (60, 30), 0, 0, 180, 0, -1)

# Save and display the image
cv.imwrite("emoji.jpg", photo)
cv.imshow('emoji', photo)
cv.waitKey(10000)
cv.destroyAllWindows()
```

### Task 4.2: Crop and Swap Parts of Two Images

This task involves cropping parts of two images and swapping them.

#### Code

```python
import cv2
import numpy as np

# Load images
img1 = cv2.imread('nature1.png')
img2 = cv2.imread('nature2.jpg')

# Crop parts from both images
cimg1 = img1[100:250, 200:500]
cimg2 = img2[100:250, 100:500]

# Swap the cropped parts
img1[100:250, 200:500] = cimg2
img2[100:250, 100:500] = cimg1

# Display the swapped images
cv2.imshow('Swapped Image 1', img1)
cv2.waitKey()
cv2.destroyAllWindows()

cv2.imshow('Swapped Image 2', img2)
cv2.waitKey()
cv2.destroyAllWindows()
```

### Task 4.3: Combine Two Images to Form a Collage

This task involves combining two images to create a collage.

#### Code

```python
import cv2
import numpy as np

# Load images
j1 = cv2.imread("joey4.jpeg")
j2 = cv2.imread("joey3.jpeg")

# Resize images to the same shape
jo = j2[:414, :700]
j0 = j1[:, :700]

# Combine images horizontally
collage_img = np.hstack((jo, j0))

# Display the combined image
cv2.imshow('Collage', collage_img)
cv2.waitKey()
cv2.destroyAllWindows()
```

## Conclusion

This guide provides basic instructions for creating, manipulating, and combining images using OpenCV and NumPy. These tasks cover fundamental operations that can be expanded for more complex image processing projects.

Thank you for exploring image processing with OpenCV and NumPy!
```

Feel free to adjust the content or formatting as needed for your specific project or audience!
