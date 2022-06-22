### Ex No: 2
### Date: 

# <p align="center"> Image-Acquisition-from-Web-Camera </p>
## Aim
 
Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Use VideoCapture(0) to access web camera
<br>

### Step 2:
Use imread to read the video or image
<br>

### Step 3:
Use imwrite to save the image
<br>

### Step 4:
Use imshow to show the video
<br>

### Step 5:
End the program and close the output video windows by pressing 'q'.
<br>

## Program:
``` Python
### Developed By: Srinivasan S
### Register No: 212220230048

## i) Write the frame as JPG file

import cv2
videoCaptureObject = cv2.VideoCapture(0)
while(True):
    ret,frame = videoCaptureObject.read()
    cv2.imshow("apple.jpg",frame)
    result = False
videoCaptureObject.release()
cv2.destroyAllWindows()


## ii) Display the video
import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret,frame = cap.read()
    cv2.imshow('frame', frame)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()



## iii) Display the video by resizing the window

import cv2
import numpy as np
cap=cv2.VideoCapture(0)

while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    
    image=np.zeros(frame.shape, np.uint8)
    smaller_frame=cv2.resize(frame, (0,0), fx=0.5, fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame
    
    cv2.imshow('frame', image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()



## iv) Rotate and display the video

import cv2
import numpy as np
cap=cv2.VideoCapture(0)

while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    
    image=np.zeros(frame.shape, np.uint8)
    smaller_frame=cv2.resize(frame, (0,0), fx=0.5, fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=image[height//2:, :width//2] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=image[height//2:, width//2:] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
    
    cv2.imshow('frame', image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## Output

### i) Write the frame as JPG image

![Screenshot 2022-04-18 192633](https://user-images.githubusercontent.com/103049243/163823732-591d9607-585c-422e-ad4f-fce509f86359.png)

### ii) Display the video

![Screenshot 2022-04-18 192719](https://user-images.githubusercontent.com/103049243/163823754-25baa4db-7fec-476b-8230-ccce41eb72fd.png)

### iii) Display the video by resizing the window

![Screenshot 2022-04-18 192743](https://user-images.githubusercontent.com/103049243/163823781-c66af9eb-272f-4b67-b8ac-6e9dfb640f84.png)

### iv) Rotate and display the video

![Screenshot 2022-04-18 192801](https://user-images.githubusercontent.com/103049243/163824019-53a24ac4-b383-4db3-b768-6d0fa22d5cb9.png)

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
