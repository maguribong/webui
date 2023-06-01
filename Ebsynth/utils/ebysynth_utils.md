# Ebsynth.md 설명

## Download `ebsynth_util.zip`
This is a modified version of the ebsynth_utility extension, which allows you to use some of its features locally. You can download it from [here](https://github.com/s9roll7/ebsynth_utility).

## Usage

1. **Install opencv-python (Only required for the first time)**

   Use this command to install opencv-python:
    ```bash
    pip install opencv-python
    ```

2. **Create Keyframes (stage2)**

   Run this command to create keyframes:
    ```bash
    python run_stage2.py input.mp4 ./input ./video_key 10 300 8.5 7
    ```

3. **Create Ebsynth Project (stage5)**

   Run the following script to create the Ebsynth project:
    ```bash
    python run_stage5.py ./input ./key out-
    ```

4. **Smoothly Connect Videos (stage7)**

   Use the last script to smoothly connect all the videos:
    ```bash
    python run_stage7.py input.mp4 out-
    ```


