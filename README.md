# DeepFace: AI-Powered Face Swapping and Enhancement

[![Python 3.9](https://img.shields.io/badge/python-3.9-blue.svg)](https://www.python.org/downloads/release/python-390/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

DeepFace is a user-friendly application that uses artificial intelligence to seamlessly swap faces in images and videos. You can also enhance face quality using advanced AI techniques, filter out unsuitable content, and even perform real-time face swaps using your webcam.

**Key Goal:** To provide a simple and effective way to explore AI-powered face manipulation.

## What Can You Do with DeepFace?

*   **Swap faces in photos:** Change the faces in your pictures to create fun or unique images.
*   **Swap faces in videos:** Replace faces in your favorite videos with ease.
*   **Enhance face quality:** Make faces in photos and videos look sharper and more detailed.
*   **Live face swapping:** Transform your face in real-time using your webcam, great for virtual meetings or streaming.
*   **Map faces:**  Control which source faces are used for which target faces.
*   **Filter NSFW Content:**  Protect yourself by blocking the processing of inappropriate content.

## Installation

1.  **Get the Code:** Download the project files from GitHub.
  - Clone by lệnh nì nhó
    ```bash
    git clone https://github.com/Trungnef/DeepFace.git 
    ```

2.  **Go to the Project Folder:** Move into the directory.

    ```bash
    cd DeepFace
    ```

3.  **Install Tools:** Make sure your computer has the necessary tools.
  - First, just create your own env
    ```bash
    python -m venv .venv
    ```
  - Now, just active your env nhó
    ```bash
    .\.venv\Scripts\activate
    ```
  - Install all necessary library nè 
    ```bash
    pip install -r requirements.txt
    ```

5.  **Install FFmpeg:**
    DeepFace uses FFmpeg to process videos. Download and install FFmpeg if you don't have it: [https://ffmpeg.org/](https://ffmpeg.org/).

    Make sure FFmpeg is added to your system's PATH, so it can be found by the program.

    And use 2 models from HuggingFace here:
    
     5.1. [GFPGANv1.4](https://huggingface.co/hacksider/deep-live-cam/resolve/main/GFPGANv1.4.pth)

     5.2. [inswapper_128.onnx](https://huggingface.co/hacksider/deep-live-cam/resolve/main/inswapper_128.onnx)

    Remember place these files in the "**/models**" folder.

## How to Use DeepFace

### Method 1: Easy Graphical Interface (GUI)

1.  **Start the App:** Open the application by running the following command:
  - with your CPU (Absolutely lag lòi tòi phòi)
    ```bash
    python run.py
    ```
  - with your GPU (Recommend mượt như sunshine)
    ```bash
    python run.py --execution-provider cuda
    ```

2.  **Choose Images/Videos:** Use the buttons to select the image or video containing the face you want to swap *from* (source) and the image or video where you want to swap *to* (target).
3.  **Adjust Settings:** Click "Show Options" to access additional settings:
    *   **Keep fps**: Keep original frame rate for video
    *   **Keep audio**: Keep audio of target video
    *   **Face Enhancer**: Enhance face quality
    *   **Many faces**:  Process multiple faces in a target
    *   **Fix Blueish Cam:**  Corrects the color of some camera inputs.
    *   **Map faces**: Select each source face for target face
    *   **Show FPS:** Shows the frame rate of the webcam preview
    *    **Mouth Mask**: Applies a mask around the mouth for better blending
    *   **Show Mouth Mask Box:** Visualizes the mouth mask area (for adjustments).
4.  **Start Processing:** Click "Start" to begin face swapping or enhancing.
5.  **Preview:** If you want to see a test result on a single frame, click "Preview".
6.  **Live Face Swap:**  Choose your camera from the dropdown menu and then select "Live" to start real-time face swapping with your webcam.

### Method 2: Advanced Command Line

If you prefer to use the command line, here's how:

```bash
python run.py -s <source_image> -t <target_file> -o <output_file> [options]
 ```

-s <source_image>: The picture of the face you want to use (the "source").

-t <target_file>: The picture or video where you want to swap the faces (the "target").

-o <output_file>: Where the result will be saved.

Common Options:
* --frame-processor <processor1> <processor2> ...: Apply processors such as face_swapper or face_enhancer.
* --keep-fps: Keep original frame rate for videos.
* --keep-audio: Keep original audio for videos.
* --many-faces: Swap all detected faces.
* --nsfw-filter: Blocks processing of inappropriate content.
* --map-faces: Use face mapping to control which source faces are used for which target faces.
* --mouth-mask: Apply a mask around the mouth for better blending
* --video-encoder: Choose the video format.
* --video-quality: Adjust video quality.
* --max-memory: Limit RAM usage.
* --execution-provider: Choose processor (cpu, cuda, coreml, dml).
* --live-mirror: Mirror the live webcam preview.
* --execution-threads : Choose thread number for processing video.
* --live-resizable: Makes the live webcam preview resizable.

# Contributing
Contributions are welcome! If you encounter any issues or have ideas for new features, please feel free to open an issue or submit a pull request.
