# Gesture-Recognition
This project aims to recognize hand gestures using Python and OpenCV, without the use of any datasets. Hand gesture recognition is a field of study within computer vision that involves detecting and interpreting human hand gestures using visual input from a camera or other sensors. There are various applications of hand gesture recognition, including human-computer interaction, sign language interpretation, and virtual reality.

The approach used in this project is based on the idea of counting defects in the contour of the hand. A defect is defined as a point where the angle between the fingers is less than 90 degrees. This approach is often used for recognizing gestures with a small number of fingers extended, as the defects correspond to the points where the fingers meet the palm.

The program is able to recognize five gestures:

+ Number 1: formed by extending the index finger
+ Number 2: formed by extending the index and middle fingers
+ Number 3: formed by extending the index, middle, and ring fingers
+ Number 4: formed by extending the index, middle, ring, and pinky fingers
+ Number 5: formed by extending all five fingers


In addition to these gestures, the program can also recognize the following:

+ "Best of luck": formed by crossing the index and middle fingers
+ "OK": if the ratio of the area of the contour of the hand to the area of the bounding box is greater than 27, the program will recognize the "OK" gesture instead. This is included as a way to differentiate between the three-finger gesture and other similar gestures, such as the "peace" or "victory" signs.

## Requirements
+ Python 3
+ OpenCV

## Installation
To install the necessary dependencies, run the following command:
```
  pip install -r requirements.txt
```

To run the program, use the following command:
```
python main.py
```

Then, place your hand within the ROI frame of the camera. The recognized gesture will be displayed on the screen.

## Algorithm
The algorithm used in this program consists of the following steps:

1. Capture a frame from the camera.
2. Pre-process the frame to enhance the contrast and remove noise. This is done using a combination of Gaussian blur and adaptive thresholding.
3. Find the contours of the hand in the frame.
4. Select the contour with the largest area, as this is likely to correspond to the hand.
5. Approximate the contour using a polygon with a fixed number of sides. This is done using the Douglas-Peucker algorithm.
6. Compute the defects of the contour, which are points where the angle between the fingers is less than 90 degrees.
7. Count the number of defects and use this to determine the gesture.

## Performance
The performance of the program will depend on the lighting conditions and the size and shape of the hand. In general, the program works best in well-lit environments and with hands that are not too small or too large. The program may not work well in low light conditions or with hands that have a highly irregular shape.

## Future Work
There are several ways in which the program could be improved in the future:
+ Add the ability to recognize more gestures
+ Improve the robustness of the program to work with a wider range of hand sizes and shapes.
+ Use machine learning techniques to improve the accuracy of the gesture recognition. One possibility would be to train a classifier using a dataset of hand gestures. This would allow the program to learn from examples and potentially improve its performance on a wider range of inputs.
+ Implement additional pre-processing steps to improve the quality of the input frames. This could include techniques such as color correction or background subtraction.
+ Explore the use of additional sensors, such as depth cameras, to improve the accuracy and robustness of the gesture recognition.
+ Develop a user interface that allows the user to easily configure the program and view the recognized gestures. This could include options such as the ability to adjust the threshold for determining defects or to select which gestures should be recognized.
+ Integrate the program into a larger application or system, such as a virtual reality game or a sign language translation tool.

## Conclusion
This project has demonstrated the feasibility of using Python and OpenCV to recognize hand gestures without the use of any datasets. While the current program has some limitations and could be improved in various ways, it represents a solid foundation for further development and experimentation.

*This Readme was written by ChatGPD.*
