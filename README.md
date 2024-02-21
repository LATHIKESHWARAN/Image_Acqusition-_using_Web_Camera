# Image_Acqusition-_using_Web_Camera
## Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.

i) Write the frame as JPG 

ii) Display the video 

iii) Display the video by resizing the window

iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Import OpenCV Package.
<br>

### Step 2:
Capture Video from Webcam. Use VideoCapture(0) to access the webcam and start capturing video.
<br>

### Step 3:
Read Video or Image. Utilize 'imread' to read a video frame or image from the webcam.
<br>

### Step 4:
Save Image to File. Employ 'imwrite' to save the captured image to a file.
<br>

### Step 5:
Display Video or Image. Use 'imshow' to display the captured video frame or image, and end Program with 'q'. Allow the program to be terminated by pressing the 'q' key.
<br>

## Program:
``` Python
### Developed By:LATHIKESHWARAN J
### Register No:212222230072

## i) Write the frame as JPG file

import cv2
videoCaptureObject = cv2.VideoCapture(0)
while (True):
    ret,frame = videoCaptureObject.read()
    cv2.imwrite("img.jpeg",frame)
    result = False
videoCaptureObject.release()
cv2.destroyAllWindows()



## ii) Display the video

import cv2
videoCaptureObject = cv2.VideoCapture(0)
while(True):
    ret,frame = videoCaptureObject.read()
    cv2.imshow('myimage',frame)
    if cv2.waitKey(1) == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()


## iii) Display the video by resizing the window

import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read() 
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8) 
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5) 
    image[:height//2, :width//2] = smaller_frame
    image[height//2:, :width//2] = smaller_frame
    image[:height//2, width//2:] = smaller_frame 
    image [height//2:, width//2:] = smaller_frame
    cv2.imshow('myimage', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()



## iv) Rotate and display the video

import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read() 
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8) 
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5) 
    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[:height//2, width//2:] = smaller_frame 
    image [height//2:, width//2:] = smaller_frame
    cv2.imshow('myimage', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()






```
## Output

### i) Write the frame as JPG image
![img](https://github.com/LATHIKESHWARAN/Image_Acqusition-_using_Web_Camera/assets/119393556/3ab7b204-8bc6-4d53-a0ae-c05aa72277eb)

</br>
</br>


### ii) Display the video
![Screenshot 2024-02-21 114751](https://github.com/LATHIKESHWARAN/Image_Acqusition-_using_Web_Camera/assets/119393556/045866e2-204d-4d6d-8ff9-8ac0598ed363)

</br>
</br>


### iii) Display the video by resizing the window
![Screenshot 2024-02-21 114824](https://github.com/LATHIKESHWARAN/Image_Acqusition-_using_Web_Camera/assets/119393556/54db0186-b2be-48a9-8ad3-e3cf95893282)

</br>
</br>



### iv) Rotate and display the video
![Screenshot 2024-02-21 114850](https://github.com/LATHIKESHWARAN/Image_Acqusition-_using_Web_Camera/assets/119393556/ade85727-3e6f-41f4-9fa0-138286924265)

</br>
</br>





## Result:
Thus the image is accessed from webcamera and displayed using openCV.
