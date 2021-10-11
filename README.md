## **Social Distancing Analyzer with Face mask detection **

Considering the big change that the world is facing, as well as our lives due to the COVID-19, we provide to people and companies a complete open-source tool to analyze the social distancing for streets, parks, offices, and even crowded places like malls, train stations, and others. 

Here you have the code and everything that you'll need to perform your own intrinsic and extrinsic calibration, and run a YOLOv4 based object detection model to track the people in a warped space and analyze how far or close they are to each other (Social Distancing).

The current pipeline only supports videos, but you can use the base classes, and methods to extend the application to video streamings, pictures and adapt it to your own project or application. Here, we will explain the dependencies, the code, and everything that you need to rock and roll!

**Status**: Archive (code is provided as-is, no updates expected)

<p align="center">
<img src="./media/figures/social_distancing_demo.gif" alt="drawing" width="1000"/>
</p>

<sub>#computer-vision #Ai #object-detection #yolo #yolo4 #python3 #Docker #covid19 #extrinsic #intrinsic #calibration #social-distancing #OpenCV #OpenSource #image-processing #deep-learning </sub>

---
### **Install Anaconda Environment**

Anaconda is the preferred method of installing SafeDistanceDetector dependencies on Linux Systems (Only for Extrinsic and Intrinsic calibration process). Anaconda is a data science platform for scientific computing and makes managing machine learning libraries significantly easier. Native installation of these libraries is possible, but native un-installation of these libraries can be significantly painful and introduce significantly much more bloat. which is why We DO not will not be supporting that method of installation.

To download the installer, follow this link and download the Anaconda platform for Linux x64. https://www.anaconda.com/distribution/#linux.

After installing the platform, you might need to add conda command into your path for further usage of the platform. You can do this with the following commands.

    export PATH=~/anaconda3/bin:$PATH
    conda init bash
    # Restart your shell
    
---
### **Install SafeDistanceDetector Environment**

You will now need to create the social distancing analyser environment with the required dependencies and libraries (provided in ```requirements.txt```). 

To create and to activate the environment, run:

    conda create -n distancing_analyser -c main python=3.6.8
    conda activate distancing_analyser
    python -m pip install -r ./Safe-Distance-Detector/requirements.txt

After this, fork this repo and make sure that your environment is activated and you are in the root path. Again, this environment is only for Intrinsic (If needed) and Extrinsic calibration scripts, you can not run nothing related to object detection on this environment.

[![License](https://img.shields.io/badge/License-Apache2-blue.svg)](https://www.apache.org/licenses/LICENSE-2.0)

## Getting started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

### Prerequisites and Installing

Install `anaconda with python3` from https://www.anaconda.com/products/enterprise/

```bash
# Tensorflow CPU
conda env create -f conda-cpu-env.yml
conda activate cpu-env

# Tensorflow GPU
conda env create -f conda-gpu-env.yml
conda activate gpu-env
```
#### Downloading official pretrained weights of YOLOv3 - Social Distancing Detection
You can download the yolov3 weights by clicking [here](https://td.angerycat.ml/yolov3.weights) then save them to the weights folder.

#### Saving your yolov3 weights as a TensorFlow model.
Load the weights using `load_weights.py` script. This will convert the yolov3 weights into TensorFlow .ckpt model files!
```
# yolov3
python load_weights.py
```
#### Downloading official pretrained weights of YOLOv3 - Face Mask Detection 

You can download the yolov3 - Face Mask Detection weights by clicking [here](https://td.angerycat.ml/yolov3_mask.weights) then save them to the weights_mask folder.

#### Saving your yolov3 weights as a TensorFlow model.
Load the weights using `load_weights_mask.py` script. This will convert the yolov3 weights into TensorFlow .ckpt model files!
```
# yolov3
python load_weights_mask.py
```

### Test with a video - Social Distancing

Exectute the file `detect_video.py` script. This will execute the same social distancing algorithms and give a live output on the screen . use the flag `--output` for saving the output file with your prefered name.
uncomment line number `277` to view the live graph outputs. 
```bash
python detect_video.py --video test.mp4 --output test_result.mp4 --output_csv test_csv.csv
```
### Test with a video - Face Mask Detection

Identify the presence of Face Mask among the people in a video by executing `detect_video_mask.py` script. This will yield a live output on your screen.
```bash
python detect_video_mask.py --video test_mask.mp4 --output test_mask_output.mp4
```

## Built with

* [Python](https://python.org) - Programming language which has been used
* [Yolo v3](https://pjreddie.com/darknet/yolo/) - To handle object detection


## License

This project is licensed under the Apache 2 License - see the [LICENSE](LICENSE) file for details
