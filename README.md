# Image-Capture-and-Video-Processing-Using-OpenCV
##Aim:

To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:
```
 Write the frame as a JPG file
 Display the video
 Display the video by resizing the window
 Rotate and display the video
 🛠️ Software Used
 Anaconda – Python 3.7
 Jupyter Notebook / VS Code
 OpenCV (cv2)
 ⚙️ Algorithm
```
Step 1:
Import the required libraries and initialize the webcam using cv2.VideoCapture().

Step 2:
Capture frames continuously from the webcam.

Step 3:
Save a frame as a JPG image using cv2.imwrite().

Step 4:
Display the live video stream using cv2.imshow().

Step 5:
Resize the frame and rotate it using OpenCV functions, then display the processed frames.

💻 Program
Developed By:
Name: _Pradeep.M
Register No:212225220071
Write the frame as JPG image
```
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time
cap = cv2.VideoCapture(0)
ret, frame = cap.read()
if ret:
    cv2.imwrite("photo.jpg", frame)
cap.release()
captured_image = cv2.imread('photo.jpg')
plt.imshow(captured_image[:,:,::-1])
plt.title('Captured Frame')
plt.axis('off')
plt.show()
```
Display the video
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
 Display the video by resizing the window
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
Rotate and display the video
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

Output
i) Write the frame as JPG image
Captured image is saved as captured_image.jpg

<img width="622" height="481" alt="Screenshot 2026-10-31 160529" src="https://github.com/user-attachments/assets/1dc0f818-8626-4a9d-9a02-cee756d3fe45" />

ii) Display the video
Live webcam video is displayed

<img width="562" height="420" alt="Screenshot 2026-10-31 160538" src="https://github.com/user-attachments/assets/e61a7176-1ace-4ca1-b5d3-91d5c41c19e2" />

iii) Display the video by resizing the window
Video is shown in resized resolution (640 × 480)

<img width="271" height="422" alt="Screenshot 2026-10-31 160544" src="https://github.com/user-attachments/assets/34b2852f-9f84-4d9f-b74c-920e62541289" />

iv) Rotate and display the video
Video is displayed after rotation (90° clockwise)

<img width="306" height="427" alt="Screenshot 2026-10-31 160551" src="https://github.com/user-attachments/assets/1b3edcc8-6dce-47e7-9a83-13c5360a8ee6" />

Result
Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.
