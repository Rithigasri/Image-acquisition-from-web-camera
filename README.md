# IMAGE AQUISITION FROM WEB CAMERA
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
Import cv2 and capture the video using cv2.VideoCapture(0).
### Step 2:
Write the captured image using cv2.imwrite("pic.jpg",frame).
### Step 3:
Resize the image using cv2.resize(frame, (0,0), fx = 0.5, fy=0.5).
### Step 4:
Display the image until the loop gets over.
### Step 5:
Rotate the image using cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180).

## PROGRAM:
```
Developed By: RITHIGA SRI.B
Register No: 212221230083
```
```
# 1.Write the frame as JPG file
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while(True):
    ret,frame = videoCaptureObject.read()
    cv2.imwrite("pic.jpg",frame)
    result = False
videoCaptureObject.release()
cv2.destroyAllWindows()

# 2.Display the video
import cv2
object=cv2.VideoCapture(0)
while(True):
    ret,frame=object.read()
    cv2.imshow('myimage',frame)
    if cv2.waitKey(1)==ord('q'):
        break
object.release()
cv2.destroyAllWindows()

# 3.Display the video by resizing the window
import numpy as np
import cv2
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
    image[height//2:, width//2:] = smaller_frame

    cv2.imshow('frame', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

# 4.Rotate and display the video
import numpy as np
import cv2
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    
    image = np.zeros(frame.shape, np.uint8)
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:,: width//2] = smaller_frame
    image[:height//2, width//2:] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, width//2:] = smaller_frame


    cv2.imshow('frame', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## OUTPUT:

### (i) Write the frame as JPG image:
![image](https://user-images.githubusercontent.com/93427256/225625720-444eb273-7de7-4527-a4a5-273318bc1f51.png)

### (ii) Display the video:
![image](https://user-images.githubusercontent.com/93427256/225627166-82d4d301-1156-41ea-a0f1-2182062bbd55.png)

### (iii) Display the video by resizing the window:
![image](https://user-images.githubusercontent.com/93427256/225627617-53b577bf-c50d-4dbc-8dee-b24018d6fd2f.png)
### iv) Rotate and display the video
![image](https://user-images.githubusercontent.com/93427256/225627923-7695c823-2c44-4a70-8ad7-7d0c6467ac4b.png)


## RESULT:
Thus the image is accessed from webcamera and displayed using openCV.
