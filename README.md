# sign-languauge-interpreter

The following repository contains the code for "An Approach on Sentence Generation using Sign Language Detection", which was presented in the International Conference on Signal Processing, Computation, Electronics, Power and Telecommunication (IconSCEPT) Karaikal.

The project in this repo was completely inspired by [Nicholas Renotte](https://github.com/nicknochnack) and his wonderful YouTube Video [Real Time Sign Language Detection with Tensorflow Object Detection and Python | Deep Learning SSD](https://youtu.be/pDXdlXlaCco) tutorial, and the source code for this github was inspired by [youngsoul](https://github.com/youngsoul/sign-language-detection-with-tfod2/tree/master).

## Caveats

* This repo was only tested on MacOS, Ventura

* This repo worked as of, June 10, 2023

## Steps

### [1] Create a conda environment

1. Have Anaconda or Miniconda installed from their website: https://docs.anaconda.com/free/anaconda/install/index.html   

2. Once the installation is done, run the following command: 

`conda create -n venv`


### [2] Activate Virtual Env

ACTIVATE THE VIRTUAL ENV

Or you will pollute your global python environment badly

`conda activate venv`

Install all the required packages

`pip install -r requirements.txt`

All of the libraries that I used are listed in `setup.py`

### [3] Update scripts/model_config.py file

* update TEMPLATE_ROOT_DIR

to Fully-Qualified Path to this repo root

* Make sure you have a section in the MODELS_CONFIG dictionary for the model you are interested in trying

* Search for TODO and update as appropriate

### [4] Setup Object Detection

Run the script:

`python scripts/setup-tf2-obj-detection.py`

This will perform a number of steps to setup TFOD models.  See the script for details, but the summary list is below:

     1 Clone Tensorflow Repos Dir

     2 Install the Object Detection API

     3 Verify TF ObjDet Install

     4 Fix tf_util bug

Sometimes, tensorflow object detection might nut run successfully. To overcome this issue, you can git clone tensorflow object detection and create a temporary or permananent route to that location to run the code. Follow this blog for reference: https://medium.com/@viviennediegoencarnacion/how-to-setup-tensorflow-object-detection-on-mac-a0b72fbf470a

### [12] Detect in Video (Thank you Tanner Gilbert)

You are now ready to run inferences.  In the case of the sign language project we want to capture images from the webcam.

`python scripts/detect_from_video.py`

### [13] Detect in Image (Thank you Tanner Gilbert)

If you are detecting objects in images use the:

`python script/detect_from_image.py`

See that file for the parameters.
