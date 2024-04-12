# Mood-Detection-w-OpenCV

Mood detection is the process of identifying and understanding a person's current emotional state. It can be done through a variety of methods, but we will focus on Facial expression recognition. Facial expressions are one of the most important cues for understanding human emotions. Mood detection systems can use computer vision techniques to analyze facial features and identify specific expressions, such as happiness, sadness, fear and anger. This project detects emotions with accuracy in real-time using OpenCV and DeepFace.

Here are the steps taken to create the provided code:

1. **Import necessary libraries**: The code imports the required libraries such as `cv2` for computer vision tasks and `DeepFace` for facial analysis.

2. **Load the face cascade classifier**: The code loads the pre-trained face cascade classifier using `cv2.CascadeClassifier`. This classifier is used to detect faces in the frames.

3. **Start capturing video**: The code initializes the capture of video frames using `cv2.VideoCapture(0)`. The argument `0` represents the default camera.

4. **Process frames in a loop**: The code enters a continuous loop to process each frame of the captured video.

5. **Capture frame-by-frame**: Within the loop, the code uses `cap.read()` to read the next frame from the video capture. The returned values `ret` and `frame` represent the success status and the captured frame, respectively.

6. **Convert frame to grayscale**: Each frame is converted from the BGR color format to grayscale using `cv2.cvtColor()`.

7. **Convert grayscale frame to RGB format**: The grayscale frame is converted to the RGB format using `cv2.cvtColor()`. This step is necessary for facial analysis.

8. **Detect faces in the frame**: The code uses the face cascade classifier to detect faces in the grayscale frame. This is done using `face_cascade.detectMultiScale()`, which returns the coordinates and dimensions of the detected faces.

9. **Extract face ROI**: For each detected face, the code extracts the face Region of Interest (ROI) from the RGB frame by cropping the region defined by the face coordinates and dimensions.

10. **Perform emotion analysis**: The extracted face ROI is passed to `DeepFace.analyze()` for emotion analysis. The `actions` parameter is set to `['emotion']` to specifically analyze the emotions in the face. The `enforce_detection` parameter is set to `False` to skip face detection if a face is already detected.

11. **Determine the dominant emotion and its confidence score**: The code retrieves the dominant emotion and its confidence score from the analysis result. The dominant emotion is determined using `result[0]['dominant_emotion']`, and the confidence score is obtained from `result[0]['emotion'][emotion]`. The confidence score is limited to a maximum of 1.0 using `min(emotion_confidence, 1.0)`.

12. **Draw rectangle and label on the frame**: The code draws a rectangle around the detected face using `cv2.rectangle()` and labels it with the predicted emotion and its confidence score using `cv2.putText()`.

13. **Display the resulting frame**: The code displays the processed frame in a window named `'Live Emotion Detector'` using `cv2.imshow()`.

14. **Exit the loop**: The loop continues until the user presses the 'q' key. Once the 'q' key is pressed, the loop breaks and the program proceeds to release the video capture and close all windows.

15. **Release the capture and close windows**: The code releases the video capture resources using `cap.release()` and closes all open windows using `cv2.destroyAllWindows()`.



![image](https://github.com/Lloydzxc/Mood-Detection-w-OpenCV/assets/163873889/fe6490d6-debe-4907-b423-1bb11615ebc5)
