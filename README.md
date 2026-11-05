# Image Segmentation Using Thresholding Techniques in OpenCV

## Aim

To segment an image using Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding techniques using Python and OpenCV.

The program performs the following operations:

- Global Thresholding
- Adaptive Thresholding
- Otsu's Thresholding

## Software Used

- Anaconda – Python 3.7
- Jupyter Notebook / VS Code
- OpenCV (cv2)
- NumPy
- Matplotlib

## Algorithm

### Step 1:

Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:

Load the input image using OpenCV.

### Step 3:

Convert the input image into grayscale format.

### Step 4: Global Thresholding

- Select a fixed threshold value.
- Apply thresholding to separate foreground and background pixels.
- Display the thresholded image.

### Step 5: Adaptive Thresholding

- Compute threshold values for small regions of the image.
- Apply Adaptive Mean Thresholding.
- Apply Adaptive Gaussian Thresholding.
- Display the segmented images.

### Step 6: Otsu's Thresholding

- Automatically determine the optimal threshold value.
- Apply Otsu's thresholding technique.
- Display the segmented image.

### Step 7:

Compare the results obtained from Global, Adaptive, and Otsu's thresholding methods.

## Program
---
## Developed By

**Name:** Mahema A








**Register No:** 212225230164

---
### Original Grayscale Image
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
img = cv2.imread('image23.jpg')

if img is None:
    print("Image not found!")
else:
    print("Image loaded successfully")
gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)

plt.imshow(gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
plt.show()


```

### Global Thresholding
```
ret, global_thresh = cv2.threshold(
    gray, 127, 255, cv2.THRESH_BINARY
)

plt.figure(figsize=(10,5))

plt.subplot(1,2,1)
plt.imshow(gray, cmap='gray')
plt.title("Original Image")

plt.subplot(1,2,2)
plt.imshow(global_thresh, cmap='gray')
plt.title("Global Thresholding")

plt.show()

```
### Adaptive Thresholding

```
adaptive_mean = cv2.adaptiveThreshold(
    gray, 255,
    cv2.ADAPTIVE_THRESH_MEAN_C,
    cv2.THRESH_BINARY,
    11, 2
)

plt.imshow(adaptive_mean, cmap='gray')
plt.title("Adaptive Mean Thresholding")
plt.axis('off')
plt.show()
adaptive_gaussian = cv2.adaptiveThreshold(
    gray, 255,
    cv2.ADAPTIVE_THRESH_GAUSSIAN_C,
    cv2.THRESH_BINARY,
    11, 2
)

plt.imshow(adaptive_gaussian, cmap='gray')
plt.title("Adaptive Gaussian Thresholding")
plt.axis('off')
plt.show()
```

### Otsu's Thresholding
```
otsu_value, otsu_thresh = cv2.threshold(
    gray, 0, 255,
    cv2.THRESH_BINARY + cv2.THRESH_OTSU
)

plt.imshow(otsu_thresh, cmap='gray')
plt.title("Otsu's Thresholding")
plt.axis('off')
plt.show()

print("Otsu Threshold Value:", otsu_value)

```

### Compare all the image

```
plt.figure(figsize=(15,8))

images = [
    (gray, "Original Grayscale"),
    (global_thresh, "Global Thresholding"),
    (adaptive_mean, "Adaptive Mean"),
    (adaptive_gaussian, "Adaptive Gaussian"),
    (otsu_thresh, "Otsu Thresholding")
]

for i, (image, title) in enumerate(images):
    plt.subplot(2,3,i+1)
    plt.imshow(image, cmap='gray')
    plt.title(title)
    plt.axis('off')

plt.tight_layout()
plt.show()
print("Image Segmentation Completed Successfully!")


```





## Output

### Original Grayscale Image

- The grayscale version of the input image is displayed.
- Serves as the input for thresholding operations.
<img width="645" height="335" alt="Screenshot 2026-11-05 203506" src="https://github.com/user-attachments/assets/18e8c0f6-d858-44ea-bdb6-b3a248c8571f" />



### Global Thresholding

- Original image is displayed.
- Thresholded image is displayed.
- A fixed threshold value is used for segmentation.
- Pixels are classified as foreground or background
<img width="903" height="281" alt="Screenshot 2026-11-05 203511" src="https://github.com/user-attachments/assets/2839c450-2a3e-42f3-88a7-8ff2fc19a75b" />
.

### Adaptive Thresholding

- Original image is displayed.
- Adaptive Mean Thresholded image is displayed.
- Adaptive Gaussian Thresholded image is displayed.
- Threshold values vary across different regions of the image.
- Suitable for images with uneven illumination.

<img width="610" height="337" alt="Screenshot 2026-11-05 203518" src="https://github.com/user-attachments/assets/84319446-d95e-4ea5-b0ea-8c197baec7b6" />

<img width="580" height="345" alt="Screenshot 2026-11-05 203529" src="https://github.com/user-attachments/assets/f91f8734-5223-4ebd-9f82-968c842e69a6" />


### Otsu's Thresholding

- Original image is displayed.
- Otsu segmented image is displayed.
- Optimal threshold value is calculated automatically.
- Produces improved segmentation for bimodal histograms.
<img width="582" height="355" alt="Screenshot 2026-11-05 203537" src="https://github.com/user-attachments/assets/42e6c7b0-5fb3-46de-a92e-0171261a0790" />

### Compare all the image
<img width="1458" height="692" alt="Screenshot 2026-11-05 203551" src="https://github.com/user-attachments/assets/c76ba557-0acb-4f67-b633-483c78e3d1fd" />


## Result

Thus, image segmentation is successfully performed using **Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding** techniques in OpenCV. 
