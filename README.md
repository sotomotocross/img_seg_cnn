# Image_segmentation_ROS_implementation
This is a ROS package consisting of a set of packages running a trained NN for the coastline detection through the ZED stereocamera inside a simulator's synthetic environment.


## The ecatkin_ws
This is a ROS workspace consisting of a set of packages running a trained NN for the coastline detection through the ZED stereocamera inside the simulator's synthetic environment.
This ROS worskpace needs to be build and run using Python3. For this reason the user has to setup a python3 virtual environment and installing a set of dependencies inside.
Also if you are an NVIDIA user then you have to check the CUDA versions, and cuDNN. Else you will be running the NN prediction on your CPU (either way the payload to the computer is heavy but GPU acceleration helps a lot).
The basic dependencies for the python3 are installed using the bellow commands:
```
$ cd ~
$ sudo apt update
$ sudo apt upgrade
$ sudo apt install build-essential cmake unzip pkg-config
$ sudo apt install libxmu-dev libxi-dev libglu1-mesa libglu1-mesa-dev
$ sudo apt install libjpeg-dev libpng-dev libtiff-dev
$ sudo apt install libavcodec-dev libavformat-dev libswscale-dev libv4l-dev
$ sudo apt install libxvidcore-dev libx264-dev
$ sudo apt install libgtk-3-dev
$ sudo apt install libopenblas-dev libatlas-base-dev liblapack-dev gfortran
$ sudo apt install libhdf5-serial-dev
$ sudo apt install python3-dev python3-tk python-imaging-tk
```
After installing the dependencies you have to install Anaconda 3 (https://docs.anaconda.com/anaconda/install/linux/) for the Ubuntu 18.04 version.
After the Anaconda installation you create an anaconda virtual environment with the following terminal commands:
```
$ source ~/anaconda3/etc/profile.d/conda.sh
$ conda create -n tf-gpu-cuda10 tensorflow-gpu=1.14 cudatoolkit=10.0 python=3.6
$ conda activate tf-gpu-cuda10
$ conda install -c conda-forge keras=2.2.5
$ pip install keras-segmentation
```
Now you have to be inside the virtual environment so you have to install all the pip dependencies:
```
$ pip install numpy
$ pip install scipy matplotlib pillow
$ pip install imutils h5py==2.10.0 requests progressbar2
$ pip install cython
$ pip install scikit-learn scikit-build scikit-image
$ pip install opencv-contrib-python==4.4.0.46
$ pip install tensorflow-gpu==1.14.0
$ pip install keras==2.2.5
$ pip install opencv-python==4.4.0.42
$ pip install keras-segmentation
$ pip install rospkg empy
```
Now you have to check the import of the keras and tensorflow:
```
$ python
$ >>> import tensorflow
$ >>>
$ >>> import keras
$ Using TensorFlow backend.
$ >>>
$ >>> import keras_segmentation
$ >>>
```
If everything succesful you can check your python 3 virtual environment running the image-segmentation-keras tutorial (https://github.com/divamgupta/image-segmentation-keras) with the dataset given from the framework. It takes about 4-6 hours (depending on the PC's we have tested till this day) so you can leave at night. If all the predictions are ok then your python 3 virtual environment is ready for use.

The setup of the ecatkin_ws ROS workspace will be given below.
