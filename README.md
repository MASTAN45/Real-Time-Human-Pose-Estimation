# Advanced Pose and Action Detection

This repository provides a real-time pose and action detection system using **OpenCV** and **MediaPipe**. The application can detect and analyze human body poses, recognize common actions, track multiple people, and provide posture feedback. It also features a stylish overlay that displays real-time information such as action recognition, posture status, and FPS.

## Features

- Real-Time Pose Detection: Uses MediaPipe to detect human body landmarks in real time.
- **Action Recognition**: Identifies common actions like "Hands Raised", "Waving", "Walking", etc., based on body posture.
- **Person Tracking**: Detects and tracks multiple people using a face detection method.
- **Posture Analysis**: Provides feedback on body posture (e.g., "Excellent posture", "Poor posture") and tips for improvement.
- **Stylish Overlay**: Displays an aesthetic overlay with information such as FPS, person count, detected action, and posture feedback.

## Requirements

To run this project, you’ll need the following libraries installed:

- OpenCV: `pip install opencv-python`
- MediaPipe: `pip install mediapipe`
- NumPy: `pip install numpy`

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/advanced-pose-action-detection.git
   cd advanced-pose-action-detection
   ```

2. Install dependencies:
   ```bash
   pip install opencv-python mediapipe numpy
   ```

3. Run the main script:
   ```bash
   python main.py
   ```

## How It Works

### 1. Pose Detection
Using MediaPipe's Pose solution, the system detects and tracks key body landmarks in real time. These landmarks are used to recognize human body poses, which are essential for the action and posture analysis.

### 2. Person Tracking
The system uses a face detection model (Haar cascades) to track multiple people in the frame. Each detected person is assigned a unique ID, and the system continuously tracks their movement across frames.

### 3. Action Recognition
Once the body landmarks are detected, the system recognizes common actions based on the relative positions of key body parts (e.g., wrist, shoulder, hip). Actions include:
- "Hands Raised"
- "Waving"
- "Talking on the Phone"
- "Walking"
- "Leaning"
- "Neutral Posture"

### 4. Posture Analysis
The system analyzes body posture by evaluating the alignment of the shoulders, hips, and back angle. It provides feedback on the user’s posture, offering suggestions for improvement, such as:
- **Excellent posture**
- **Good posture**
- **Fair posture**
- **Poor posture**

### 5. Stylish Overlay
An attractive overlay is generated and displayed on the video feed, providing real-time feedback on the detected action, posture, and FPS. The overlay includes:
- FPS (Frames per second)
- Person count (number of people detected)
- Action (e.g., "Hands Raised")
- Posture (e.g., "Good posture")
- Posture advice (e.g., "Try to keep your shoulders level and back straight.")

## Code Overview

The core functionality is encapsulated in the `AdvancedPoseDetector` class, which contains the following methods:

- `findPose(img)`: Detects body landmarks and draws them on the image.
- `getPosition(img)`: Extracts and returns the body landmarks' positions.
- `track_persons(img)`: Tracks faces in the image and assigns unique IDs to each person.
- `recognize_action(lmList)`: Recognizes actions based on the positions of the wrist, elbow, shoulder, and other key landmarks.
- `analyze_posture(lmList)`: Analyzes the user’s posture and provides feedback on it.
- `create_stylish_overlay(img, info)`: Generates a visually appealing overlay with real-time information.

The main function captures frames from the webcam, processes them in real time, and displays the output.

## Usage

After running the script, the webcam feed will be displayed with the following information:

- **FPS**: Displays the frames per second for performance monitoring.
- **Person Count**: Number of people detected in the frame.
- **Action**: The detected action (e.g., "Hands Raised").
- **Posture**: The analysis of your posture (e.g., "Excellent posture").
- **Advice**: Posture improvement advice.

Press `q` to quit the application.

 Example Output
![dl 1](https://github.com/user-attachments/assets/adfd1c7c-cf6d-4c8c-b4fc-10d22c39af9b)
![2](https://github.com/user-attachments/assets/617d26be-59d0-409d-9d09-63bd498eeb4f)
![3](https://github.com/user-attachments/assets/34edd088-49ed-4b33-a856-11d2f4a23e80)









When running the application, you will see the real-time webcam feed with a stylish overlay:

- An **FPS counter** for performance.
- A **person count** showing how many people are detected.
- **Action** recognition (e.g., "Hands raised").
- **Posture** evaluation (e.g., "Excellent posture").
- **Posture advice** to help you maintain good posture.

 Contributions

Contributions are welcome! If you'd like to contribute to this project, please fork the repository and create a pull request with your changes. Make sure to include tests for new features or bug fixes.



 Acknowledgments

- **OpenCV**: For image processing and webcam handling.
- **MediaPipe**: For pose detection and landmark tracking.
- **NumPy**: For numerical operations, such as calculating angles.
