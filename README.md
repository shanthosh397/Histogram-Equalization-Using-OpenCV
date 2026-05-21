# Histogram Equalization Using OpenCV (Grayscale & Color Images)

---

## Aim

To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

The program performs the following operations:

- Read and display a grayscale image  
- Plot histogram of the grayscale image  
- Apply histogram equalization on grayscale image  
- Read and display a color image  
- Plot histogram of B, G, R channels  
- Convert image to HSV color space  
- Apply histogram equalization on the Value (V) channel  
- Convert the enhanced image back to BGR format  
- Display original and enhanced images with histograms  

---

## Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib  

---

## Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the image `parrot.jpg` in grayscale format.

### Step 3:
Display the grayscale image and plot its histogram.

### Step 4:
Apply histogram equalization using `cv2.equalizeHist()` to enhance contrast.

### Step 5:
Display original grayscale image, its histogram, enhanced image, and its histogram using a 2 × 2 grid.

### Step 6:
Read the same image in color format.

### Step 7:
Split the image into B, G, R channels and plot their histograms.

### Step 8:
Convert the image from BGR to HSV color space.

### Step 9:
Apply histogram equalization on the V (Value) channel.

### Step 10:
Merge the channels and convert the image back to BGR format.

### Step 11:
Display original color image, histogram, enhanced image, and enhanced histogram using a 2 × 2 grid.

---

## Program

### Developed By:
**Name:** Shanthosh G 
**Register No:** 2305003008

### Ex. No. 02

#### 1. import libraries.
```python
import cv2
import matplotlib.pyplot as plt

```
#### 2. Read grayscale image.
```python
Gray_image = cv2.imread("WhatsApp Image 2026-05-12 at 14.16.29.jpeg", 0)

```
#### 3. Display Gray Scale Image.
```python
plt.figure(figsize=(6,6))
plt.imshow(Gray_image, cmap='gray')
plt.title("Gray Scale Image")
plt.axis("off")
plt.show()

```
#### 4. Read color image.
```python
Color_image = cv2.imread("WhatsApp Image 2026-05-12 at 14.32.43.jpeg")

```
#### 5.Convert BGR to RGB.
```python
Color_rgb = cv2.cvtColor(Color_image, cv2.COLOR_BGR2RGB)

```
#### 6.Display Color Image.
```python
plt.figure(figsize=(6,6))
plt.imshow(Color_rgb)
plt.title("Color Image")
plt.axis("off")
plt.show()

```
#### 7.Histogram of Gray Scale Image.
```python
hist_gray = cv2.calcHist([Gray_image], [0], None, [256], [0,256])

plt.figure(figsize=(8,5))
plt.title("Histogram of Gray Scale Image")
plt.xlabel("Pixel Intensity")
plt.ylabel("Pixel Count")
plt.plot(hist_gray, color='black')
plt.xlim([0,256])
plt.show()

```
#### 8.Histogram of Blue Channel.
```python
hist_blue = cv2.calcHist([Color_image], [0], None, [256], [0,256])

plt.figure(figsize=(8,5))
plt.title("Histogram of Blue Channel")
plt.xlabel("Pixel Intensity")
plt.ylabel("Pixel Count")
plt.plot(hist_blue, color='blue')
plt.xlim([0,256])
plt.show()

```
#### 9.Histogram Equalization.
```python
equalized = cv2.equalizeHist(Gray_image)
```
#### 10.Histogram of Equalized Image
```python
hist_equalized = cv2.calcHist([equalized], [0], None, [256], [0,256])

plt.figure(figsize=(8,5))
plt.title("Histogram of Equalized Image")
plt.xlabel("Pixel Intensity")
plt.ylabel("Pixel Count")
plt.plot(hist_equalized, color='green')
plt.xlim([0,256])
plt.show()
```


##  Output

### Grayscale Histogram Equalization

- Original grayscale image is displayed
<img width="523" height="364" alt="image" src="https://github.com/user-attachments/assets/6c14ebd8-9515-4c26-bc64-3e23db945c1b" />

- Histogram of original grayscale image is plotted
<img width="597" height="389" alt="image" src="https://github.com/user-attachments/assets/cb50a1ad-e60b-41b6-9289-3bec4d6247ba" />
 

### Color Image Histogram Equalization

- Original color image is displayed
<img width="502" height="360" alt="image" src="https://github.com/user-attachments/assets/f954f34a-3469-4817-910e-39bc20891d51" />

- Histogram of B, G, R channels is plotted
<img width="608" height="388" alt="image" src="https://github.com/user-attachments/assets/c37cf6b3-a9e5-4851-ac7e-dd615a414c0b" />
  

### Equalization Image 

- Display Equalized Image
<img width="506" height="363" alt="image" src="https://github.com/user-attachments/assets/2185f423-6d7e-4daf-b52b-db97119c6fbc" />

- Histogram of Equalized Image
<img width="593" height="406" alt="image" src="https://github.com/user-attachments/assets/6935317c-529e-41c9-9ff2-c92029864f86" />



## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
