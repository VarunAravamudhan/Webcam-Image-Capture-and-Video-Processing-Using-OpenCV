# Image Capture and Video Processing Using OpenCV

---

## Aim

To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

1. Write the frame as a JPG file  
2. Display the video  
3. Display the video by resizing the window  
4. Rotate and display the video  

---

## 🛠️ Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  

---

## ⚙️ Algorithm

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

## 💻 Program
### i) Write the frame as JPG image

```python
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

### ii) Display the video

```python
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

### iii) Display the video by resizing the window

```python
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()

    if not ret:
        break

    resized_frame = cv2.resize(frame, (100, 150))

    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)

    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()

    time.sleep(0.05)

cap.release()
```

### iv) Rotate and display the video

```python
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

### Developed By:
**Name:** Varun A 

### Register No:
212224240178
---

## Output

### i) Write the frame as JPG image
Captured image is saved as `captured_image.jpg

<img width="656" height="512" alt="image" src="https://github.com/user-attachments/assets/f9c04799-7161-48fd-917c-8eab63e77857" />


### ii) Display the video
Live webcam video is displayed

<img width="787" height="638" alt="Screenshot 2026-11-17 084656" src="https://github.com/user-attachments/assets/8994d7ec-a7e8-488b-9599-9b8ed020f6a4" />



### iii) Display the video by resizing the window
Video is shown in resized resolution (640 × 480)

<img width="802" height="635" alt="image" src="https://github.com/user-attachments/assets/53d611fc-6ffb-4f6c-b4e4-004268e81598" />


### iv) Rotate and display the video
Video is displayed after rotation (90° clockwise)

<img width="597" height="840" alt="image" src="https://github.com/user-attachments/assets/3315cc5e-6ea8-4aa6-919d-410bdc7b2216" />

---

## Result

Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.
