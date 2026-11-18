### NAME: SURYA P <br>
### REG NO: 212224230280 <br> 
### Date: 26/10/2026

## EX. No. 2 : Record Image Acquisition using Web Camera

## Aim:

To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

1. Write the frame as a JPG file  
2. Display the video  
3. Display the video by resizing the window  
4. Rotate and display the video  

---

## Software Used:

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  

---

## Algorithm:

### Step 1:
Import the required libraries and initialize the webcam using `cv2.VideoCapture()`.

### Step 2:
Capture frames continuously from the webcam.

### Step 3:
Save a frame as a JPG image using `cv2.imwrite()`.

### Step 4:
Display the live video stream using `cv2.imshow()`.

### Step 5:
Resize the frame and rotate it using OpenCV functions, then display the processed frames.

---

## Program:

### Developed By:
**Name:** Surya P
**Register No:** 212224230280

---

## Output:

### i) Write the frame as JPG image
Captured image is saved as `captured_image.jpg`
```
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time
cap = cv2.VideoCapture(0)
ret, frame = cap.read()
if ret:
    cv2.imwrite("captured_frame.jpg", frame)
cap.release()
captured_image = cv2.imread('captured_frame.jpg')
plt.imshow(captured_image[:,:,::-1])
plt.title('Captured Frame')
plt.axis('off')
plt.show()
```

<img width="672" height="522" alt="Screenshot 2026-11-18 224202" src="https://github.com/user-attachments/assets/ca9c1b85-ca77-42cb-9135-3c91f5be17ec" />



### ii) Display the video
Live webcam video is displayed
```
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```
<img width="675" height="505" alt="Screenshot 2026-11-18 224233" src="https://github.com/user-attachments/assets/c3d4730a-2e51-4051-9379-ef5aecc04ca3" />




### iii) Display the video by resizing the window
Video is shown in resized resolution (640 × 480)
```
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    resized_frame = cv2.resize(frame, (100, 150))  # Resize to 320x240
    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```
<img width="387" height="510" alt="Screenshot 2026-11-18 224309" src="https://github.com/user-attachments/assets/6fb72092-f84e-42c6-8ff6-7ae7e6280ff8" />



### iv) Rotate and display the video
Video is displayed after rotation (90° clockwise)
```
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    rotated_frame = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)
    frame_rgb = cv2.cvtColor(rotated_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```

<img width="382" height="505" alt="image" src="https://github.com/user-attachments/assets/dd7dfa1f-b99b-4193-aa08-e4ec6f68fd95" />


---


## Result:

Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.
