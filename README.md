# EXP-2-Record-Image-Acquisition-using-Web-Camera

## Aim
To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

Write the frame as a JPG file
Display the video
Display the video by resizing the window
Rotate and display the video
## 🛠️ Software Used
Anaconda – Python 3.7
Jupyter Notebook / VS Code
OpenCV (cv2)
## ⚙️ Algorithm
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

## Program
Developed By: S.AISHWARIYA

Register No:212224240005

i) Write the frame as JPG image
```
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

<img width="677" height="501" alt="Screenshot 2026-05-13 195903" src="https://github.com/user-attachments/assets/3a30f0ae-c126-42cd-ba76-ed22901d80f9" />

ii) Display the video
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
<img width="718" height="485" alt="image" src="https://github.com/user-attachments/assets/4c843c99-cce7-460d-99ac-4cf1108da65c" />
 
iii) Display the video by resizing the window
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
    time.sleep(0.02)

cap.release()

```
<img width="479" height="473" alt="image" src="https://github.com/user-attachments/assets/0e44a2e1-0b79-4de0-b6c9-f41098d7d182" />


iv) Rotate and display the video
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
<img width="464" height="479" alt="image" src="https://github.com/user-attachments/assets/c7de1e62-e00c-4884-ba5e-4986f23a7729" />

## Result
Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.
