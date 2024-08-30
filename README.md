#About this project:

1. cv2 is the opencv library module in python. This library provides function for image processing and computer vision task.

2. face_cascade = cv2.CascadeClassifier(cv2.data.haarcascades + 'haarcascade_frontalface_default.xml')
^^ cv2.cascade classifier is the function that loads up pretrained model for detecting objects. In this case it is used for face detection.

3. cv2.data.haarcascades is a path to the directory containing haarcascade file provided by opencv. 

4. haarcascade_frontalface_default.xml this xml file contains the trained model data for detecting frontal faces.

5. cv2.VideoCapture(0) opens the default camera on your system. The argument zero refers to the first camera device. If you have multiple cameras, you can specify other indices eg, 1, 2, 3.

5. Loop to continuously get frames - 
while True:
    ret, frame = cap.read()
cap.read() captures the frames from the webcam, it returns 2 values:
I. ret - this is a boolean indicating if the frame was captured successfully.
II. frame - captures frames itself

6. Convert frame to grayscale - 
 gray = cv2.cvtColor(frame, cv2.COLOR_BGR2GRAY)
cv2.cvtColor converts the image from one color space to another.
cv2.COLOR_BGR2GRAY specifies the conversion from BGR color space to grayscale
Note: grayscale images are simpler and into the efficiency of face detection

7. facecascade.detectmultiscale - detects the object faces in the image

8. scale factor specifies how much the image can be reduced at each image scale. 1.1 means image size is reduced by 10% at each scale. 

9. minneighbors specifies how many neighbors each candidate rectangle should have to retain it. 

10. minsize - minimum size of the face detect smaller values detect smaller faces.
