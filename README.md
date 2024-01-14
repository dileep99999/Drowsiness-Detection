# Methodology
The Main objective is to obtain the eye state from the image frames and classify it into one of the two classes below.
	1. Drowsy (Eyes closed consistently),
	2. Active (Eyes are open Consistently)

A customized Deep Learning can be built to obtain the above goal but it has lot of issues like Lighting conditions, shaky videos and vision based problems.
These issues can be avoided by using a famous Deep Learning Models i.e., Transfer Learning Models.
# Proposed Model 
In this section, the related work must be categorized into three parts, those related to the Face and eyes detection, fed images to transfer learning model and detection of drowsiness using proposed methods.
OpenCV is an open source library that can be used to perform task like face detection and this can be done by using Haar cascade classifier. 
To detect the face from image ,the Haar features are used such as, The first two are “edge features” used to detect edges. The third is a “line feature”, while the fourth is a “four rectangle feature”, most likely used to detect a slanted line.
After detection of face using Haar cascade classifier, the resulting images are converted into grey scale images and then fed into transfer learning model which is Inception V3 .
The proposed model is Inception v3 have proved to be more computationally efficient, both in terms of the number of parameters generated by the network and the economical cost incurred (memory and other resources) in comparison to VGGNet, Inception Networks (GoogleNet/Inception v1).
This model converts the eye images from RGB to grey scale images and predicts the output by using the final softmax layers. 
The model detects whether the eyes are closed or open for certain amount of time. If the eyes are closed for more than 12 successive frames the alarm rings it stops when both the eyes are completely open.
# Flow Chart
From incoming live video stream, image is extracted. Then the face is detected using Haarcascade face classifier from the image.
If the detection of face is successful, then both the eyes are detected using Haarcascade left eye and right eye classifiers. If face is not detected, the next frame need to be considered from video stream.
After identification of eyes, the eyes are cropped from the face and the RGB images are converted into grey scale images and this will be fed into the proposed Transfer Learning model.
The Transfer learning model Inception V3 is a deep learning model based on Convolutional Neural Networks, which is used for image classification and it classifies the eye images whether they are closed or opened.
Both the left eye and right eye are separately fed into the model.
If the model detects that both the eyes are closed for more than 12 successive frames then there is an attribute i.e.; score, which will be increased.
If the score value reaches the threshold value, then the alarm will be triggered until the score value drops below the threshold.
If the both eyes are not closed for more than 12 successive frames, then the model considers it as Blinking and it will consider the next frames for the process.



