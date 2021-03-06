# PyTorch-YOLOv3
Minimal implementation of YOLOv3 in PyTorch. 

Currently only inference using pretrained weights is supported.

## Table of Contents
- [PyTorch-YOLOv3](#pytorch-yolov3)
  * [Table of Contents](#table-of-contents)
  * [Paper](#paper)
  * [Implementation](#implementation)
      + [Installation](#installation)
      + [Inference](#inference)
  * [Credit](#credit)
  
## Paper
### YOLOv3: An Incremental Improvement
_Joseph Redmon, Ali Farhadi_ <br>

**Abstract** <br>
We present some updates to YOLO! We made a bunch
of little design changes to make it better. We also trained
this new network that’s pretty swell. It’s a little bigger than
last time but more accurate. It’s still fast though, don’t
worry. At 320 × 320 YOLOv3 runs in 22 ms at 28.2 mAP,
as accurate as SSD but three times faster. When we look
at the old .5 IOU mAP detection metric YOLOv3 is quite
good. It achieves 57.9 AP50 in 51 ms on a Titan X, compared
to 57.5 AP50 in 198 ms by RetinaNet, similar performance
but 3.8× faster. As always, all the code is online at
https://pjreddie.com/yolo/.

[[Paper]](https://pjreddie.com/media/files/papers/YOLOv3.pdf) [[Original Implementation]](https://pjreddie.com/yolo/)

## Implementation

### Installation
    $ git clone https://github.com/eriklindernoren/PyTorch-YOLOv3
    $ cd PyTorch-YOLOv3/
    $ sudo pip3 install -r requirements.txt
    $ cd weights/
    $ bash download_weights.sh

### Inference
Below table displays the inference times when using as inputs images scaled to 256x256. The ResNet backbone measurements are taken from the YOLOv3 paper. The Darknet-53 measurement shows the inference time of this implementation on my 1080ti card.

| Backbone                | FPS      |
| ----------------------- |:--------:|
| ResNet-101 (Titan X)    | 53       |
| ResNet-152 (Titan X)    | 37       |
| Darknet-53 (1080ti)     | 76       |

    $ python3 test.py --image_folder /data/samples

<p align="center"><img src="assets/giraffe.png" width="480"\></p>
<p align="center"><img src="assets/dog.png" width="480"\></p>
<p align="center"><img src="assets/traffic.png" width="480"\></p>
<p align="center"><img src="assets/messi.png" width="480"\></p>

## Credit
Inspired by https://github.com/ayooshkathuria/pytorch-yolo-v3
