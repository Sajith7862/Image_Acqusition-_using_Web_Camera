# Image-Acquisition-from-Web-Camera
## AIM:

To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## SOFTWARE USED:
Anaconda - Python 3.7
## ALGORITHM:
### Step 1:
Use cv2.VideoCapture(0) to access web camera
<br>

### Step 2:
Use cv2.imread to read the video or image
<br>

### Step 3:
Use cv2.imwrite to save the image
<br>

### Step 4:
Use cv2.imshow to show the video
<br>

### Step 5:
End the program and close the output video window by pressing 'q'.
<br>

## PROGRAM:
``` Python
### Developed By: Mohamed Hameem Sajith J
### Register No: 212223240090

## i) Write the frame as JPG file
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



## ii) Display the video
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



## iii) Display the video by resizing the window
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




## iv) Rotate and display the video
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
## OUTPUT:

### i) Write the frame as JPG image
<img width="512" height="411" alt="image" src="https://github.com/user-attachments/assets/f6d7f628-58c6-47e6-b5af-c3572f377ec0" />




</br>
</br>


### ii) Display the video
<img width="512" height="389" alt="image" src="https://github.com/user-attachments/assets/bdc658aa-1214-4dca-b8ad-337fb2da44f8" />


</br>
</br>


### iii) Display the video by resizing the window
<img width="266" height="389" alt="image" src="https://github.com/user-attachments/assets/918c6f23-d55b-4d4f-8368-8ced3cf666f5" />



</br>
</br>



### iv) Rotate and display the video

<img width="297" height="389" alt="image" src="https://github.com/user-attachments/assets/0b17d8a6-e5f6-430a-8c87-4bdf06588b20" />


</br>
</br>


## RESULT: 
Thus the image is accessed from webcamera and displayed using openCV.
