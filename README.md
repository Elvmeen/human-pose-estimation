# Human Pose Estimation

A real-time human pose estimation demo built with **MediaPipe Pose Landmarker** and browser camera APIs. It detects body landmarks from a live webcam stream, draws a connected human skeleton, and estimates selected joint angles.

## Live demo

After deployment, open the hosted website over HTTPS and allow camera access.

## Features

- Real-time pose detection from a webcam
- Body landmark and skeleton visualization
- Support for detecting up to two people
- Estimated left/right elbow and knee angles
- Pose count, visible landmark count, frame count, and approximate processing FPS
- Start, stop, and reset controls
- Responsive interface for desktop and mobile screens
- Camera frames are processed in the browser and are not uploaded by this application

## Technology

- HTML, CSS, and JavaScript
- MediaPipe Tasks Vision — Pose Landmarker
- Browser MediaDevices API for webcam access
- Canvas API for drawing landmarks and skeleton connections

## Run locally

1. Download or clone this repository.
2. Open a terminal in the project folder.
3. Start a local web server. For example:

   ```bash
   python -m http.server 8000
   ```

4. Open `http://localhost:8000` in a modern browser.
5. Select **Start camera** and allow camera access.

A local server is recommended because browsers restrict camera access on insecure pages. HTTPS is required when using the deployed version.

## How it works

1. The browser requests permission to use the webcam.
2. MediaPipe Pose Landmarker loads its pretrained pose model.
3. Each available video frame is passed to the model.
4. The model returns body landmarks for detected people.
5. Canvas draws the pose connections and landmark points over the video.
6. Selected joint angles are estimated from the 2D coordinates of three landmarks.

## Notes and limitations

- This project uses a pretrained model. It does not train a new neural network.
- Angle values are 2D estimates and can change with camera position and body orientation.
- Detection quality depends on lighting, camera quality, and whether the person's body is visible.
- The first launch requires an internet connection to load MediaPipe and its model files.
- GPU acceleration is requested first. Browser or device compatibility may affect performance.

## Repository

https://github.com/Elvmeen/human-pose-estimation

## License

MIT
