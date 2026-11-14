# Exp-6- Record-EDGE DETECTION

## Experiment Details

- **Name:** Dharshini J
- **Register Number:** 212224240036

## Aim

To perform edge detection using Sobel, Laplacian, and Canny edge detectors.

## Software Required

- Anaconda
- Python 3.7
- OpenCV
- NumPy
- Matplotlib

## Algorithm

**Step 1:** Import all the necessary libraries required for the program.

**Step 2:** Load the input image using the `cv2.imread()` function.

**Step 3:** Convert the input image into grayscale using `cv2.cvtColor()`.

**Step 4:** Apply the Sobel operator using `cv2.Sobel()` to detect edges in the horizontal and vertical directions.

**Step 5:** Combine the horizontal and vertical Sobel edges using `cv2.magnitude()`.

**Step 6:** Apply the Laplacian operator using `cv2.Laplacian()` to detect edges in the image.

**Step 7:** Apply the Canny edge detector using `cv2.Canny()` to identify the edges.

**Step 8:** Display the original image and all the detected edges using Matplotlib.

## Program

### Developed By: Dharshini J

### Register Number: 212224240036

### i) Original Image

```python id="d7f5wk"
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread("my image.jpg")

# Convert the image to grayscale
gray_image = cv2.cvtColor(
    image, cv2.COLOR_BGR2GRAY
)

# Display the original image
plt.imshow(
    cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
)

plt.title("Original Image")
plt.axis("off")
plt.show()
```

**Output:**

<img width="347" height="417" alt="image" src="https://github.com/user-attachments/assets/a4b07cb9-bc24-4a58-90b9-9ba1cbd542d2" />


## 1. Sobel Edge Detector

### Program

```python id="f9zv2k"
# Sobel in X direction
sobel_x = cv2.Sobel(
    gray_image, cv2.CV_64F, 1, 0, ksize=5
)

# Sobel in Y direction
sobel_y = cv2.Sobel(
    gray_image, cv2.CV_64F, 0, 1, ksize=5
)

# Combine both directions
sobel_combined = cv2.magnitude(
    sobel_x, sobel_y
)

# Display Sobel edges
plt.imshow(sobel_combined, cmap="gray")
plt.title("Sobel Edge Detection")
plt.axis("off")
plt.show()
```

**Output:**

<img width="322" height="403" alt="image" src="https://github.com/user-attachments/assets/f947c0d8-d7fc-454c-bbfc-3403ae1d561d" />


## 2. Laplacian Edge Detector

### Program

```python id="u8w3rp"
laplacian = cv2.Laplacian(
    gray_image, cv2.CV_64F
)

# Display Laplacian edges
plt.imshow(laplacian, cmap="gray")
plt.title("Laplacian Edge Detection")
plt.axis("off")
plt.show()
```

**Output:**

<img width="328" height="402" alt="image" src="https://github.com/user-attachments/assets/32aef99c-ede0-43c1-9970-f34d921bda6a" />



## 3. Canny Edge Detector

### Program

```python id="z3m8qy"
canny_edges = cv2.Canny(
    gray_image, 50, 150
)

# Display Canny edges
plt.imshow(canny_edges, cmap="gray")
plt.title("Canny Edge Detection")
plt.axis("off")
plt.show()
```

**Output:**

<img width="318" height="402" alt="image" src="https://github.com/user-attachments/assets/fb7744d8-b1cb-458c-a141-3db587515e44" />



## Result

Thus, the edges of the input image were successfully detected using Sobel, Laplacian, and Canny edge detectors with OpenCV and Python.
