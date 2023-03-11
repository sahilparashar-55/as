You will learn about Automatic number-plate recognition. We will use the Tesseract OCR An Optical Character Recognition Engine (OCR Engine) to automatically recognize text in vehicle registration plates.

Python-tesseract:
Py-tesseract is an optical character recognition (OCR) tool for python. That is, it’ll recognize and “read” the text embedded in images. Python-tesseract is a wrapper for Google’s Tesseract-OCR Engine. It is also used as an individual script, because it can read all image types like jpeg, png, gif, bmp, tiff, etc. Additionally, if used as a script, Python-tesseract will print the recognized text rather than writing it to a file. It has ability to recognize more than 100 languages.
Installation:

pip install pytesseract
OpenCV:
OpenCV is an open source computer vision library. The library has more than 2500 optimized algorithms. These algorithms are often used to search and recognize faces, identify objects, recognize scenery and generate markers to overlay images using augmented reality, etc.

Installation:

pip install opencv-python
Note: make sure you installed pytesseract and OpenCV-python modules properly
Note: you should have the dataset ready and all images should be as shown below in image processing techniques for best performance; dataset folder should be in same folder as you are writing this python code in or you will have to specify the path to dataset manually wherever needed.

Procedure:
# Loading the required python modules
import pytesseract # this is tesseract module
import matplotlib.pyplot as plt
import cv2 # this is opencv module
import glob
import os
Note: the name of image files has to be the exact number in respective license plate image. example: if you have a with license plate having number as “FTY349U” then name the image file as “FTY349U.jpg”.
Now we have the plates predicted but we haven’t seen what is the prediction, so to view the data and prediction we do a bit of visualization as shown below. we are also calculating the accuracy of prediction without using any built-in function.
We see that the Tesseract OCR engine mostly predicts all of the license plates correctly with 100% accuracy. For the license plates, the Tesseract OCR Engine predicted incorrectly (i.e. GWT2180, OKV8004, JSQ1413), we will apply image processing techniques on those license plate files and pass them to the Tesseract OCR again. Applying the image processing techniques would increase the accuracy of the Tesseract Engine for the license plates of GWT2180, OKV8004, JSQ1413.
Code: Image Processing Techniques
Image resizing:
Resize the image file by a factor of 2x in both the horizontal and vertical directions using cv2.resize
Converting to Gray-scale: Next, we convert our resized image file to gray scale to optimize the detection and reduce the amount of colors present in image drastically which will help in the detection of license plates easily.
Denoising the Image:
Gaussian Blur is a technique for denoising images. it makes the edges more clearer and smoother which in-turn makes the characters more readable.
Now, pass the transformed license plate file to the Tesseract OCR engine and see the predicted result.
Similarly, do this image processing for all other number plates that didn’t get 100% accuracy. Finally, the license plate detection model is ready
