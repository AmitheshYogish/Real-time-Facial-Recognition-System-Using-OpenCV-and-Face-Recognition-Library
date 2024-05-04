# Real-time-Facial-Recognition-System-Using-OpenCV-and-Face-Recognition-Library

## Overview:
The provided code is a face recognition system implemented in Python using the OpenCV library. It consists of two main files: `main.py` and `simple_facerec.py`. The system aims to detect faces in a live video stream from a webcam and recognize them if they match with the pre-encoded faces stored in a specified folder.

## Complete Workflow:
1. Import Libraries: Both `main.py` and `simple_facerec.py` begin with importing necessary libraries, including OpenCV (`cv2`) and the custom module `SimpleFacerec`.

2. Encoding Faces: Within both files, an instance of the `SimpleFacerec` class is created. This class handles the encoding of faces from images stored in a folder. The method `load_encoding_images()` is called to load the images for encoding.

3. Camera Initialization: After encoding faces, the code initializes the webcam using OpenCV's `VideoCapture()` function. This sets up a connection to the default camera (index 0).

4. Face Detection and Recognition Loop: Both files enter an infinite loop (`while True`) where they continuously read frames from the webcam using `cap.read()`. Within this loop:
   - The `detect_known_faces()` method of the `SimpleFacerec` class is used to detect faces in the current frame and recognize known faces.
   - For each detected face, a rectangle is drawn around it using `cv2.rectangle()`, and the name of the recognized person is displayed above the rectangle using `cv2.putText()`.
   - The modified frame with face rectangles and labels is displayed in a window using `cv2.imshow()`.
   - The loop continues until the 'Esc' key (key code 27) is pressed.

5. Exiting the Program: Once the 'Esc' key is pressed (`key == 27`), the loop breaks, and the webcam connection is released using `cap.release()`. Finally, all OpenCV windows are closed with `cv2.destroyAllWindows()`.

Note: There's a redundancy in the code, as both `main.py` and `simple_facerec.py` perform the same operations. Typically, the encoding and face recognition functionality should be in a separate module (`simple_facerec.py`), while `main.py` should focus on utilizing this functionality for specific applications.
