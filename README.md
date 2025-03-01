# Facial Emotion Recognition (FER) using DeepFace
## Overview

This project implements real-time Facial Emotion Recognition (FER) using the `DeepFace` library and OpenCV. It captures live video from a webcam, detects faces, and predicts the dominant emotion displayed by the person in the frame. The recognized emotion is overlaid on the video feed in real-time.

This project was developed as part of a hands-on Data Science and AI course internship, focusing on Computer Vision (CV) and Deep Learning (DL).

## Features


- Real-time face detection and emotion recognition using a webcam.
- Displays the dominant emotion (e.g., happy, sad, angry) on the video feed.
- Built with `OpenCV` for video processing and `DeepFace` for emotion analysis.

## Technologies Used

- **Python**: 3.12.9
- **Libraries**:
    * `opencv-python (cv2)`: For webcam capture and image processing.
    * `deepface`: For face detection and emotion recognition.
    * `tf-keras`: Required dependency for TensorFlow compatibility.
- **IDE**: Visual Studio Code

## Prerequisites

- Python 3.12.9 (Note: DeepFace may not support Python 3.13+ due to compatibility issues).
- A working webcam.
- Virtual environment (recommended).

## Installation

1. **Clone the Repository**:
    ```
    git clone https://github.com/nmfadil/FER-using-Deepface.git
    cd FER-using-Deepface
    ```
2. **Create a Virtual Environment**:
    ```
    py -3.12 -m venv venv
    ```
3. **Activate the Virtual Environment**:
    * On Windows:
        ```
        venv\Scripts\activate
        ```
    * On macOS/Linux:
        ```
        source venv/bin/activate
        ```
4. **Install Dependencies**:
    * Using requirements.txt (recommended for exact versions):
        ```
        pip install -r requirements.txt
        ```
    * Or manually install core packages:
        
            pip install opencv-python deepface tf-keras
        
>**Note**: `tf-keras` is required if you encounter the error:
`ValueError: You have tensorflow 2.18.0 and this requires tf-keras package. Please run 'pip install tf-keras' or downgrade your tensorflow.`

## Usage

1. **Optional Configuration**: To store the `facial_expression_model_weights.h5` file *(which will be generated automatically while running the script)* in the project directory (instead of the default `C:\Users\[user]\.deepface\weights\`), uncomment the following lines in the script *before* importing `deepface`:
    ```
    import os
    current_directory = os.path.dirname(os.path.abspath(__file__))
    os.environ['DEEPFACE_HOME'] = current_directory
    ```
2. **Run the script**:
    ```
    python emorec_deepface.py
    ```
3. A window will open showing the webcam feed with the detected emotion displayed in green text.
4. Press `q` to exit the application.

## Code Explanation

- `cv2.VideoCapture(0)`: Initializes the webcam (0 is the default camera).
- `DeepFace.analyze()`: Performs face detection and emotion recognition on each frame.
- `cv2.putText()`: Overlays the dominant emotion on the video feed.
- **Error Handling**: Catches exceptions (e.g., when no face is detected).

## Sample Output

- The video feed displays text like: `Emotion: happy` when a face is detected.
- If no face is detected, an error message is printed to the console.

## Troubleshooting

- **Python Version**: Use Python 3.12.9 if you encounter issues with DeepFace on newer versions (e.g., 3.13.1).
 - **TensorFlow Compatibility**: Install `tf-keras` if you get a `ValueError` related to TensorFlow 2.18.0. Alternatively, downgrade TensorFlow if needed.
- **Webcam Issues**: Ensure your webcam is connected and not in use by another application.
- **Dependency Errors**: Verify that `opencv-python`, `deepface`, and `tf-keras` are installed correctly in your virtual environment.

## Acknowledgments

- Built as part of a Data Science and AI internship course.
- Thanks to the DeepFace library creators, OpenCV community, and tf-keras for compatibility support.

## License

This project is licensed under the MIT License - see the LICENSE file for details.
