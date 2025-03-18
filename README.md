# smileinput

Press any key with your smile

## Steps

Assume you cloned and inside the directory.

1. Get Python 3
2. Create virtual environment: `python -m venv ./.venv`
3. Get into the virtual environment: `. ./.venv/bin/activate`
4. `pip install mediapipe python-ydotool`
5. `wget -O face_landmarker_v2_with_blendshapes.task -q https://storage.googleapis.com/mediapipe-models/face_landmarker/face_landmarker/float16/1/face_landmarker.task`
6. Run: `python ./main.py --frameWidth=600 --frameHeight=400` . The lower value for `--frameWidth=` and `--frameHeight`, the more FPS you get.

## What is it?

Basically, it's a [mediapipe example](https://github.com/google-ai-edge/mediapipe-samples/blob/main/examples/face_landmarker/raspberry_pi/detect.py) for facial landmarks.

## Pros and cons

Pros:
1. It works

Cons:
1. Input is emulated on Linux via uinput kernel's module, needs a little rewrite to work on other operational systems.
2. It seems to not be accelerated on Nvidia GPUs because of mediapipe. Not that big of a problem to be honest, if set lower values for frame size to take via camera.
3. When you use it, it seems to take control of camera, so I couldn't use camera from other apps like OBS. Though, I could show my camera output and record the window on OBS, so it's just an inconvinience

## License

MIT
