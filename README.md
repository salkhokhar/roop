Take a video and replace the face in it with a face of your choice. You only need one image of the desired face. No dataset, no training.

That's it, that's the software. You can watch some demos [here](https://drive.google.com/drive/folders/1KHv8n_rd3Lcr2v7jBq1yPSTWM554Gq8e?usp=sharing).

![demo-gif](demo.gif)

## Disclaimer
Better deepfake software than this already exist, this is just a hobby project I created to learn about AI. Users must get consent from the concerned people before using their face and must not hide the fact that it is a deepfake when posting content online. I am not responsible for malicious behaviour of end-users.

To prevent misuse, it has a built-in check which prevents the program from working on inappropriate media.

## How do I install it?

**Issues according to installation will be closed without ceremony from now on, we cannot handle the number of requests.**

There are two types of installations: basic and GPU-powered.

- **Basic:** It is more likely to work on your computer but it will also be very slow. You can follow the instructions for the basic install [here](https://github.com/s0md3v/roop/wiki/1.-Installation).

- **GPU:** If you have a good GPU and are ready for solving any software issues you may face, you can enable GPU which is wayyy faster. To do this, first follow the basic install instructions given above and then follow GPU-specific instructions [here](https://github.com/s0md3v/roop/wiki/2.-GPU-Acceleration).

- For windows guys: 
1) install visual studio 2022 with desktop development C++ and python development (not sure about python development)
2) install python 3.10.x (any 3.10)
3) download the last version of roop
4) pip install virtualenv
5) virtualenv venv
6) start venv\scripts\activate.bat
7) pip install -r requirements.txt
that's for CPU (sometimes works for GPU for some reason)

- If you want Nvidia gpu to work:
don't go for CPU steps
1) install visual studio 2022 with desktop development C++ and Python development (not sure about Python development)
2) install cuda 11.7 (https://developer.nvidia.com/cuda-11-7-0-download-archive)
3) download cudnn 8.9.1 for cuda 11.x https://developer.nvidia.com/rdp/cudnn-archive
4) unpack cudnn over C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v11.7 with replacement
5) install python 3.10.x (any 3.10)
6) download the last version of roop
7) pip install virtualenv
8) virtualenv venv
9) start venv\scripts\activate.bat
10) pip install torch torchvision torchaudio --force-reinstall --index-url https://download.pytorch.org/whl/cu117
11) pip install -r requirements.txt

and yes, don't forget to download ffmpeg https://ffmpeg.org/download.html
and inswrapper_128.onnx https://drive.google.com/file/d/1eu60OrRtn4WhKrzM4mQv4F3rIuyUXqfl/view?usp=drive_link

## How do I use it?
> Note: When you run this program for the first time, it will download some models ~300MB in size.

Executing `python run.py` command will launch this window:
![gui-demo](gui-demo.png)

Choose a face (image with desired face) and the target image/video (image/video in which you want to replace the face) and click on `Start`. Open file explorer and navigate to the directory you select your output to be in. You will find a directory named `<video_title>` where you can see the frames being swapped in realtime. Once the processing is done, it will create the output file. That's it.

Don't touch the FPS checkbox unless you know what you are doing.

Additional command line arguments are given below:

```
options:
  -h, --help            show this help message and exit
  -f SOURCE_IMG, --face SOURCE_IMG
                        use this face
  -t TARGET_PATH, --target TARGET_PATH
                        replace this face
  -o OUTPUT_FILE, --output OUTPUT_FILE
                        save output to this file
  --keep-fps            maintain original fps
  --keep-frames         keep frames directory
  --all-faces           swap all faces in frame
  --max-memory MAX_MEMORY
                        maximum amount of RAM in GB to be used
  --cpu-cores CPU_CORES
                        number of CPU cores to use
  --gpu-threads GPU_THREADS
                        number of threads to be use for the GPU
  --gpu-vendor {apple,amd,intel,nvidia}
                        choice your GPU vendor
```

Looking for a CLI mode? Using the -f/--face argument will make the program in cli mode.

## Future plans
- [ ] Improve the quality of faces in results
- [ ] Replace a selective face throughout the video
- [ ] Support for replacing multiple faces

## Credits
- [henryruhs](https://github.com/henryruhs): for being an irreplacable contributor to the project
- [ffmpeg](https://ffmpeg.org/): for making video related operations easy
- [deepinsight](https://github.com/deepinsight): for their [insightface](https://github.com/deepinsight/insightface) project which provided a well-made library and models.
- and all developers behind libraries used in this project.
