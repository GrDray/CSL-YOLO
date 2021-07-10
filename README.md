# CSL-YOLO: A New Lightweight Object Detection System for Edge Computing

[![license](https://img.shields.io/github/license/mashape/apistatus.svg)](LICENSE)

This project provides a SOTA level lightweight YOLO called "Cross-Stage Lightweight YOLO"(CSL-YOLO),

it is achieving better detection performance with only 43% FLOPs and 52% parameters than Tiny-YOLOv4.

<div align=center>
<img src=https://github.com/D0352276/CSL-YOLO/blob/main/demo/result_img_1.png width=100% />
</div>

## Requirements

- [Tensorflow 2](https://www.tensorflow.org/)
- [Numpy](http://www.numpy.org/)
- [h5py](http://www.h5py.org/)
- [Python 3](https://www.python.org/)


## How to Get Started?
```bash
#Predict
python3 main.py -p cfg/predict_coco.cfg
#Train
python3 main.py -p cfg/train_coco.cfg
#Eval
python3 main.py -ce cfg/eval_coco.cfg
#Camera DEMO
python3 main.py -d cfg/demo_coco.cfg
```


## More Info

### Change Model Scale
The model's default size is 224x224, if you want to change the size of 320~512, 

please go to cfg/XXXX.cfg and change the following two parts:
```bash
# input_shape=[512,512,3]
# out_hw_list=[[64,64],[48,48],[32,32],[24,24],[16,16]]
# input_shape=[416,416,3]
# out_hw_list=[[52,52],[39,39],[26,26],[20,20],[13,13]]
# input_shape=[320,320,3]
# out_hw_list=[[40,40],[30,30],[20,20],[15,15],[10,10]]
input_shape=[224,224,3]
out_hw_list=[[28,28],[21,21],[14,14],[10,10],[7,7]]

weight_path=weights/224_nolog.hdf5

                         |
                         | 224 to 320
                         V
                         
# input_shape=[512,512,3]
# out_hw_list=[[64,64],[48,48],[32,32],[24,24],[16,16]]
# input_shape=[416,416,3]
# out_hw_list=[[52,52],[39,39],[26,26],[20,20],[13,13]]
input_shape=[320,320,3]
out_hw_list=[[40,40],[30,30],[20,20],[15,15],[10,10]]
# input_shape=[224,224,3]
# out_hw_list=[[28,28],[21,21],[14,14],[10,10],[7,7]]

weight_path=weights/320_nolog.hdf5
```

### Fully Dataset

<img src=https://github.com/D0352276/CSL-YOLO/blob/main/demo/result_table.png width=100% />
