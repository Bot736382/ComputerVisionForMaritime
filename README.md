# ComputerVisionForMaritime
This repo is a culmination of all the learnings that have been taken from the specially designed learning course. It will be using YoloV9 to carry out a bunch of processes and adapt it to maritime uses.


## Installation

This is a more customised installation compared to the installation mentioned on YoloV9's official github repo.

Docker environment (recommended). We will be using a docker container of Nvidia's PyTorch Release 21.11. Import the git clone of YoloV9 paper and the coco dataset into a single folder before installation. The ports 8888 and 6006 are reserved for this docker container for us to be able to access the Jupyter Notebook GUI and tenserboard plugins respectively.

``` shell
# create the docker container, you can change the share memory size if you have more.
nvidia-docker run --name yolov9 -it -p 8888:8888 -p 6006:6006 -v {Location of CV}/CV:/CV --shm-size=64g nvcr.io/nvidia/pytorch:21.11-py3

# apt install required packages
apt update
apt install -y zip htop screen libgl1-mesa-glx

# pip install required packages
pip install seaborn thop

# go to code folder
cd /yolov9
```

## Training a Model on New Datasets
We start of by running this. The new_data folder is basically a combination of the SeaShips dataset as can be found on: [SeaShips](http://www.lmars.whu.edu.cn/prof_web/shaozhenfeng/datasets/SeaShips%287000%29.zip)
``` shell
python train_dual.py --workers 4 --device 0 --batch 8 --data new_data/seaships.yaml --cfg models/detect/yolov9-c.yaml --weights './weights/yolov9-c.pt' --name train2_new --min-items 0 --epochs 50 --close-mosaic 15
```
