# Image-Acquisition-from-Web-Camera

## Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG. 
ii) Display the video. 
iii) Display the video by resizing the window.
iv) Rotate and display the video.

## Software Used:

Anaconda - Python 3.7

## Algorithm:

### Step 1:

Import the packages(numpy and cv2). 

### Step 2:

Use VideoCapture method to access through webcam, read the captured image and write the frame as jpg file. 

### Step 3:

Use the same VideoCapture method to display video through webcam.

### Step 4:

Now display the by resizing window image. 

### Step 5:

Now display the image by rotating it.

## Program:

``` Python
### Developed By: Vishwa Rathinam .S
### Register No: 212221240063
```

```python
## i) Write the frame as JPG file

import cv2
videoCaptureObject = cv2.VideoCapture(0)
while(True):
    ret,frame = videoCaptureObject.read()
    cv2.imwrite("NewPicture.jpg",frame)
    result = False
videoCaptureObject.release()
cv2.destroyAllWindows()
```

```python
## ii) Display the video

import numpy as np
import cv2

cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()
    cv2.imshow('frame', frame)
    if cv2.waitKey(1) == ord('v'):
        break
cap.release()
cv2.destroyAllWindows()

```


```python
## iii) Display the video by resizing the window:

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
    if cv2.waitKey(1) == ord('v'):
        break
cap.release()
cv2.destroyAllWindows()

```

```python
## iv) Rotate and display the video:

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
    if cv2.waitKey(1) == ord('v'):
        break
cap.release()
cv2.destroyAllWindows()

```


## Output:

### i) Write the frame as JPG image

![o1](https://user-images.githubusercontent.com/95266350/228018745-873abe8e-8531-4f6e-bab6-8df8626d2353.png)


### ii) Display the video

![o2](https://user-images.githubusercontent.com/95266350/228018770-7f84fcc3-f52a-4a4b-8017-54a15715da39.png)


### iii) Display the video by resizing the window

![o3](https://user-images.githubusercontent.com/95266350/228018790-49dadeba-39c8-44e4-a362-943355682fe4.png)

### iv) Rotate and display the video

![o4](https://user-images.githubusercontent.com/95266350/228018801-cdb84c6e-97e6-4954-aaa4-f22680846d51.png)


## Result:

Thus the image is accessed from webcamera and displayed using openCV.


