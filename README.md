# Image-Acquisition-from-Web-Cameraa
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
Import cv2 and capture the viedo using cv2.ViedoCapture(0).

### Step 2:
Write the capture image using cv2.imwrite("NewPicture.jpg",frame).


### Step 3:
Resize the image using cv2.resize(frame,(0,0),fx=0.5,fy=0.5).


### Step 4:
Display the image until the loop gets over.


### Step 5:
Rotate the image using cv2.rotate(smaller_frame,cv2.ROTATE_180).


## Program:
``` 
### Developed By: Dharmaraj S
### Register No:212222240025

## i) Write the frame as JPG file

import cv2
viedoCaptureObject=cv2.VideoCapture(0)
while(True):
    ret,frame=viedoCaptureObject.read()
    cv2.imwrite("NewPicture.jpg",frame)
    result=False
viedoCaptureObject.release()
cv2.destroyAllWindows()


## ii) Display the video

import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('Dharmaraj S (212222240025)',frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()


## iii) Display the video by resizing the window


import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('Dharmaraj S (212222240025)',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()


## iv) Rotate and display the video

import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('Dharmaraj S (212222240025)',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()







```
## Output

### i) Write the frame as JPG image
![Screenshot 2023-09-09 154249](https://github.com/dharmaraj-007/Image-Acquisition-from-Web-Cameraa/assets/119560386/5439678f-5b10-458e-80a7-0f4de3657d49)


### ii) Display the video
![Screenshot 2023-09-09 155306](https://github.com/dharmaraj-007/Image-Acquisition-from-Web-Cameraa/assets/119560386/084bccf6-50d9-4aef-96c6-b8c4dcbd8d22)



### iii) Display the video by resizing the window

![Screenshot 2023-09-09 155450](https://github.com/dharmaraj-007/Image-Acquisition-from-Web-Cameraa/assets/119560386/6e52ebb7-23e9-41d1-915f-2e8bcb3eb5a0)


### iv) Rotate and display the video


![Screenshot 2023-09-09 155657](https://github.com/dharmaraj-007/Image-Acquisition-from-Web-Cameraa/assets/119560386/786af322-4a75-481a-bc60-14df51f0d09b)



## Result:
Thus the image is accessed from webcamera and displayed using openCV.
