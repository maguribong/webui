# Video Processing Guide

## Steps:

1. **Download an input video**

2. **Extract Frames from the Input Video**

   Run the following command:
    ```bash
    ffmpeg -i "{INPUT_VIDEO_NAME.mp4}" -vf "fps=30,scale=768:432" "./input/%07d.png"
    ```

3. **Run ebsynth_util scripts which will create video_key**

   Execute this command:
    ```bash
    python run_stage2.py input.mp4 ./input ./video_key 10 300 8.5 7
    ```

4. **Run img2img on webui**

5. **Run QA run for one image if you are getting a satisfactory result**

   Check prompts, scale, denoising strength.

6. **Verify the Scale**

   Make sure the scale of webui is matching the input images and video!

7. **Enable Controlnet**

   Pick the lienart_realistic preprocessor and the lienart model.

8. **Run a Batch img2img Run on WebUI**

   After the QA run, run a batch img2img run on webui.

9. **Set input_key Directory and out_key Directory on Batch Run**

10. **Generate New Images**

    New images will be generated in the out_key directory with lineart images.

11. **Delete Image Keys**

    Here is the command to delete lineart images (images with '-' in the name):
    ```bash
    del *-*.png
    ```

12. **Create Ebsynth Project File**

    Run the following script to create the project file:
    ```bash
    python run_stage5.py ./input ./key out-
    ```

13. **Run ebsynth.exe**

    Execute ebsynth.exe with the created project files.

14. **Run All on ebsynth.exe**

15. **Connect All the Images**

    Run the last script to connect all the images:
    ```bash
    python run_stage7.py input.mp4 out-
    ```