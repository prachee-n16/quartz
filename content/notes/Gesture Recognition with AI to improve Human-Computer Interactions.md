---
title: "Gesture Recognition with AI to improve Human-Computer Interactions"
---

**Overall Idea**
Desktop application that can detect hand gestures/ facial expressions and use them as keybinds, allowing them to function as shortcuts or commands. 

**Implementation Details**
Part 1: Real-time Hand Gesture Recognition using TensorFlow & OpenCV

From [Developer's Google Guide on MediaPipe](https://developers.google.com/mediapipe/solutions/vision/gesture_recognizer),
With MediaPipe Gesture Recognizer,
- Recognize hand gestures in real time
- Provide landmarks of the detected hands (21 key points that it tracks)
- Handedness - which hand is being used to make gesture? This provides more options for keybinds.

![[assets/mediaPipeHandGestures.png]]

There are two model bundles - Hand Landmark and Gesture Classification.

 Hand Landmark model has both, palm detection and hand landmarks detection. 
 - Palm detection will localize the region of hands from input image.
 - Hand landmark finds landmarks on localized region and marks them

With gesture classification, it can recognize 7 common hand gestures. This can serve as a default keybind option. So, when the app opens, these 7 will be a pre-set selection but users should still have the ability to enter a custom gesture. 

How does it do it?
- Encode the image features into a [[Image Feature Vector|Feature Vector]] to feed into the model
- Lightweight gesture classifier i.e. classification model will classify it into predefined categories
