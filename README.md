# ComputerVisionForMaritime
## Installation

Docker environment (recommended). We will be using a docker container of Nvidia's PyTorch Release 21.11. Import the git clone of YoloV9 paper and the coco dataset into a single folder before installation. The ports 8888 and 6006 are reserved for this docker container for us to be able to access the Jupyter Notebook GUI and tenserboard plugins respectively.
<details><summary> <b>Expand</b> </summary>

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

</details>
