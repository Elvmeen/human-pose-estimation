# Human Pose Estimation

A simple real-time human pose estimation project. It detects body landmarks from a webcam and draws a connected skeleton over the video.

The repository includes two ways to run it:
- **Browser demo:** open the hosted page and allow camera access. It uses MediaPipe Tasks Vision in the browser.
- **Python application:** run the OpenCV + MediaPipe script on your computer.

## Live demo

The live demo will be added after deployment.

## Features

- Real-time body pose detection from a webcam.
- Skeleton visualization with connected body landmarks.
- Detection of up to two people in the browser demo.
- Live counts for detected poses and visible landmarks.
- Estimated left/right elbow and knee angles.
- Start, stop, and reset controls.
- Camera frames are processed locally in the browser; this project does not upload or store them.

## Technologies

- Python 3.10 or 3.11
- OpenCV
- MediaPipe
- HTML, CSS, and JavaScript
- MediaPipe Tasks Vision (browser demo)

## Run the browser demo locally

1. Clone or download this repository.
2. Open a terminal in the project folder.
3. Start a local web server:

   ```bash
   python -m http.server 8000
   ```

4. Visit `http://localhost:8000`.
5. Select **Start camera** and allow camera access.

A local server is recommended because browsers normally require HTTPS or localhost for camera access.

## Run the Python application

1. Install Python 3.10 or 3.11.
2. Install the dependencies:

   ```bash
   pip install -r requirements.txt
   ```

3. Run the application:

   ```bash
   python pose_estimation.py
   ```

4. Stand where your upper and lower body are visible to the camera.
5. Press `q` or `Esc` to close the application.

The Python application uses your default webcam. If needed, change `cv2.VideoCapture(0)` to another camera index in `pose_estimation.py`.

## How it works

1. OpenCV reads frames from the webcam.
2. Each frame is converted from BGR to RGB.
3. MediaPipe's pretrained Pose model detects body landmarks.
4. OpenCV draws the detected landmarks and skeleton connections.
5. The program calculates approximate elbow and knee angles from landmark coordinates.

## Notes and limitations

- This project uses a pretrained model. It does not train a new neural network.
- Detection quality depends on lighting, camera quality, distance, and body visibility.
- Joint angles are approximate 2D estimates. Camera angle and body orientation can affect them.
- The browser demo needs an internet connection on first load to download the MediaPipe library and model.
- Camera access requires permission. The hosted demo must use HTTPS.

## Repository

https://github.com/Elvmeen/human-pose-estimation

## License

MIT
