## Single-Camera Recording

### Introduction
We recommend that everybody starts by creating a single-camera recording and reconstruction of their movement  before moving on to more complex tasks like multi-camera calibration and reconstruction. 

Starting with a single-camera reconstruction will help ensure that the full pipeline works on your computer with your hardware. 

Once that is established, you'll have a great baseline understanding of the compete process before moving to the more complex task of creating a multi-camera calibration and recording
    

### Installation 

If you haven't installed FreeMoCap yet, follow the [Installation Guide](./Installation.md) to install the software. Once you've installed FreeMoCap, come back continue this tutorial.

### Launching FreeMoCap
Launch FreeMoCap from the terminal by activating the relevant Python environment and typing `freemocap` into the terminal, then press Enter. At that point, the GUI should show up, which will look like this:

[Add a screenshot of the view here]

Click the friendly button that says "Start a New Recording" and then click the button that says "Detect Cameras" :
[Add a screenshot of the view here]

### Camera Detection
The software should locate your cameras, and once they're connected, it will show a viewpoint from the connected camera in the GUI. You can adjust the settings in the sidebar and then click "Apply Settings to Cameras" to apply them. The most important setting to look at right now is the exposure setting, which you should make as low as possible to decrease blur. We generally like to keep it below -6. Adjust it downwards until the image looks crisp, which will probably make it look slightly darker than you would normally expect. For this simple single-camera recording, this isn't a crucial step. As long as you can see yourself in the image, you should be tracked okay, but it's good to keep in mind for the future.

### Recording
!!! tip-full-width "What about the Calibration?"

    This is the place where if you were using multiple cameras, you would need to perform a Charuco board-based calibration. But for now, we can move past it.

Click "Record" and go into the field of view to perform some kind of movement. Then click "Stop", and it should process automatically from there. When it's done, it will pop up a Blender scene if Blender was properly detected (TODO - add a troubleshooting tip if that doesn't happen) and populate the folder with the output files:

[Add a screenshot of the view here]

!!! tip-full-width "Why is the data flat?"

    FreeMoCap's single camera data output are 2D trajectories, reflecting the positions of the mediapipe detected joint trajectories in the recorded image. While we could use mediapipe's algorithm to make a guess at 3D positions, currently the 3D estimates from a single camera are so poor that we strongly believe that to get 3D data, you should use multiple cameras!