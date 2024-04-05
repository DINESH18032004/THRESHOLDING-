# THRESHOLDING
## Aim

### To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
### 1. Anaconda - Python 3.7
### 2. OpenCV

## Algorithm

### Step1:

Import necessary packages



### Step2:


Read the image


### Step3:

If the read image is a color image, convert it into a grayscale image



### Step4:

Perform the threshold operation you want to do(global thresholding or adaptive thresholding or otsu's thresholding)



### Step5:

Display the Results

## Developed By : DINESH KUMAR R

## Reg.No. 212222110010

## Program

```python
# Load the necessary packages

import cv2
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale


# Read the image
img = cv2.imread('panther.jpg')
o_image = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
image_path = 'panther.jpg'
image = cv2.imread(image_path, cv2.IMREAD_GRAYSCALE)

if image is None:
    raise FileNotFoundError(f"Image not found at path: {image_path}")



# Use Global thresholding to segment the image

_, binary_thresh = cv2.threshold(image, 127, 255, cv2.THRESH_BINARY)
_, binary_inv_thresh = cv2.threshold(image, 127, 255, cv2.THRESH_BINARY_INV)
_, tozero_thresh = cv2.threshold(image, 127, 255, cv2.THRESH_TOZERO)
_, tozero_inv_thresh = cv2.threshold(image, 127, 255, cv2.THRESH_TOZERO_INV)
_, truncate_thresh = cv2.threshold(image, 127, 255, cv2.THRESH_TRUNC)


# Use Adaptive thresholding to segment the image

adaptive_mean_thresh = cv2.adaptiveThreshold(image, 255, cv2.ADAPTIVE_THRESH_MEAN_C, cv2.THRESH_BINARY, 11, 2)
adaptive_gaussian_thresh = cv2.adaptiveThreshold(image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)



# Use Otsu's method to segment the image 

_, otsu_thresh = cv2.threshold(image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)


# Display the results

plt.figure(figsize=(12, 15))

# Original and Gray Image
plt.subplot(1, 2, 1)
plt.imshow(o_image)
plt.title('Original Image')
plt.axis('off')

plt.subplot(1, 2, 2)
plt.imshow(image, cmap='gray')
plt.title('Gray Iamge')
plt.axis('off')


 # Original, Threshold (Binary) and Threshold (Binary inverse)
plt.subplot(1, 2, 1)
plt.imshow(image, cmap='gray')
plt.title('Gray Image')
plt.axis('off')

plt.subplot(1, 2, 2)
plt.imshow(binary_thresh, cmap='gray')
plt.title('Binary Threshold')
plt.axis('off')

plt.subplot(1, 2, 1)
plt.imshow(binary_thresh, cmap='gray')
plt.title('Binary Threshold')
plt.axis('off')

plt.subplot(1, 2, 2)
plt.imshow(binary_inv_thresh, cmap='gray')
plt.title('Binary Inverse Threshold')
plt.axis('off')

#  Threshold (to Zero) and Threshold (to Inverse Zero)
plt.subplot(1, 2, 1)
plt.imshow(tozero_thresh, cmap='gray')
plt.title('Threshold(To Zero)')
plt.axis('off')

plt.subplot(1, 2, 2)
plt.imshow(tozero_inv_thresh, cmap='gray')
plt.title('Threshold(To Inverse Zero)')
plt.axis('off')

# Original, Threshold Image (Truncate)
plt.subplot(1, 2, 1)
plt.imshow(image, cmap='gray')
plt.title('Gray Image')
plt.axis('off')


plt.subplot(1, 2, 2)
plt.imshow(truncate_thresh, cmap='gray')
plt.title('Truncate Threshold')
plt.axis('off')

# Adaptive threshold (mean) and Adaptive threshold (Gaussian)
plt.subplot(1, 2, 1)
plt.imshow(adaptive_mean_thresh, cmap='gray')
plt.title('Adaptive Threshold (Mean)')
plt.axis('off')

plt.subplot(1, 2, 2)
plt.imshow(adaptive_gaussian_thresh, cmap='gray')
plt.title('Adaptive Threshold (Gaussian)')
plt.axis('off')



# Original, Otsu's threshold
plt.subplot(1, 2, 1)
plt.imshow(image, cmap='gray')
plt.title('Gray Image')
plt.axis('off')

plt.subplot(1, 2, 2)
plt.imshow(otsu_thresh, cmap='gray')
plt.title("Otsu's Threshold")
plt.axis('off')





```
## Output

### Original Image
<br>
<br>

![Screenshot 2024-04-05 084612](https://github.com/DINESH18032004/THRESHOLDING-/assets/119477784/24b16a84-f5d0-4667-a186-49a173eea6d0)

<br>
<br>

### Global Thresholding
<br>
<br>

![Screenshot 2024-04-05 084651](https://github.com/DINESH18032004/THRESHOLDING-/assets/119477784/bb1aef38-42a6-47c4-9350-64faf58a5186)


![Screenshot 2024-04-05 084701](https://github.com/DINESH18032004/THRESHOLDING-/assets/119477784/41d4fca0-1550-4697-a317-325c8f13f916)


![Screenshot 2024-04-05 084709](https://github.com/DINESH18032004/THRESHOLDING-/assets/119477784/c0febd85-d3cb-4e91-879e-93502c8318dd)


![Screenshot 2024-04-05 084718](https://github.com/DINESH18032004/THRESHOLDING-/assets/119477784/39899279-1c09-4093-8ff5-579ea6fad1e1)


<br>
<br>

### Adaptive Thresholding
<br>
<br>


![Screenshot 2024-04-05 084727](https://github.com/DINESH18032004/THRESHOLDING-/assets/119477784/525e4e20-4cec-4686-a3a9-b31b9068a8b1)


<br>
<br>

### Optimum Global Thesholding using Otsu's Method
<br>
<br>

![Screenshot 2024-04-05 084737](https://github.com/DINESH18032004/THRESHOLDING-/assets/119477784/2b1b30f5-d78f-4fa8-96ac-0e19ec103064)


<br>
<br>


## Result
### Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
