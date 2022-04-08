# Image-Acquisition-from-Web-Camera
## Aim
 
Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.<br>
i) Write the frame as JPG <br>
ii) Display the video <br>
iii) Display the video by resizing the window<br>
iv) Rotate and display the video<br>

## Software Used
Anaconda - Python 3.7
## Algorithm
Step 1:
Import Opencv Package.<br>

Step 2:
Capture the Video from the WebCamera.<br>

Step 3:
Write the image to a file.<br>

Step 4:
Show the image or the live camera.<br>

Step 5:
End the program.<br>

## Program:
## i) Write the frame as JPG file
``` Python
### Developed By:G Venkata Pavan Kumar
### Register No: 212221240013


```python
import cv2
video = cv2.VideoCapture(0)
while(True):
    t,frame = video.read()
    cv2.imwrite("Newpicture.jpg",frame)
    result=False
    if cv2.waitKey(1) == ord('b'):
        break
video.release()
cv2.destroyAllWindows()
```

## ii) Display the video
```python
import cv2
pic = cv2.VideoCapture(0)
while True:
    t,frame = pic.read()
    cv2.imshow('frame',frame)
    if cv2.waitKey(1) == ord('b'):
        break
pic.release()
cv2.destroyAllWindows()
```



## iii) Display the video by resizing the window
```python
import numpy as np
import cv2
im = cv2.VideoCapture(0)
while True:
    ret,frame = im.read()
    width = int(im.get(3))
    height = int(im.get(4))
    image = np.zeros(frame.shape,np.uint8)
    smallerFrame = cv2.resize(frame,(0,0),fx = 0.5,fy=0.5)
    image[:height//2,:width//2] = smallerFrame
    image[height//2:, :width // 2] = smallerFrame
    image[:height//2, width//2:] = smallerFrame
    image[height//2:, width//2:] = smallerFrame
    cv2.imshow('frame',image)
    if cv2.waitKey(1) == ord('b'):
        break
im.release()
cv2.destroyAllWindows()
```



## iv) Rotate and display the video
```python
import numpy as np
import cv2
im = cv2.VideoCapture(0)
while True:
    ret,frame = im.read()
    width = int(im.get(3))
    height = int(im.get(4))
    image = np.zeros(frame.shape,np.uint8)
    smallerFrame = cv2.resize(frame,(0,0),fx = 0.5,fy=0.5)
    image[:height//2,:width//2] = cv2.rotate(smallerFrame,cv2.ROTATE_180)
    image[height//2:, :width // 2] = smallerFrame
    image[:height//2, width//2:] = smallerFrame
    image[height//2:, width//2:] = cv2.rotate(smallerFrame,cv2.ROTATE_180)
    cv2.imshow('frame',image)
    if cv2.waitKey(1) == ord('b'):
        break
im.release()
cv2.destroyAllWindows()
```

## Output

### i) Write the frame as JPG image
![DIP1](https://user-images.githubusercontent.com/94827772/162371680-4fb7d409-7dce-4ae7-8156-e52f20a1ef50.png)


### ii) Display the video
![DIP2 ](https://user-images.githubusercontent.com/94827772/162371447-4edae789-6263-465c-91a7-ce7ca69aa5e7.png)


### iii) Display the video by resizing the window
![DIP3](https://user-images.githubusercontent.com/94827772/162371473-5132fb05-fce0-43a1-afc4-0b46fedf30d3.png)


### iv) Rotate and display the video
![DIP4](https://user-images.githubusercontent.com/94827772/162371513-4c8e08b5-bf81-4cf7-9792-343e91a8f9e0.png)

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
