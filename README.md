# SOCIAL AI

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
