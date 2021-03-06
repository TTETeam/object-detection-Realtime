# Real-time Yolov3 Object Detection for Webcam (using Tensorflow)

![alt text](https://github.com/theAIGuysCode/Object-Detection-API/raw/master/detections/detection.jpg)

## Getting started
### Conda (Recommended)

```bash
# Tensorflow CPU
conda env create -f conda-cpu.yml
conda activate yolov3-cpu

# Tensorflow GPU
conda env create -f conda-gpu.yml
conda activate yolov3-gpu
```

### Pip


```bash
# TensorFlow CPU
pip install -r requirements.txt

# TensorFlow GPU
pip install -r requirements-gpu.txt
```

### Nvidia Driver (For GPU, if you haven't set it up already)


```bash
# Ubuntu 18.04
sudo apt-add-repository -r ppa:graphics-drivers/ppa
sudo apt install nvidia-driver-430
# Windows/Other
https://www.nvidia.com/Download/index.aspx
```

### Downloading official pretrained weights
For Linux: Let's download official yolov3 weights pretrained on COCO dataset.


```bash
# yolov3
wget https://pjreddie.com/media/files/yolov3.weights -O weights/yolov3.weights

# yolov3-tiny
wget https://pjreddie.com/media/files/yolov3-tiny.weights -O weights/yolov3-tiny.weights
```

For Windows: You can download the yolov3 weights by clicking here and yolov3-tiny here then save them to the weights folder.

### Using Custom trained weights
Learn How To Train Custom YOLOV3 Weights Here: https://www.youtube.com/watch?v=zJDUhGL26iU

Add your custom weights file to weights folder and your custom .names file into data/labels folder.
### Saving your yolov3 weights as a TensorFlow model.
Load the weights using ``` load_weights.py ``` script. This will convert the yolov3 weights into TensorFlow .ckpt model files!


```bash
# yolov3
python load_weights.py

# yolov3-tiny
python load_weights.py --weights ./weights/yolov3-tiny.weights --output ./weights/yolov3-tiny.tf --tiny
```

After executing one of the above lines, you should see .tf files in your weights folder.
