
# Benchmarks for Object Detection in Aerial Images

## Introduction
This codebase is created to build benchmarks for object detection in aerial images.
It is modified from [mmdetection](https://github.com/open-mmlab/mmdetection).
The master branch works with **PyTorch 1.1** or higher. If you would like to use PyTorch 0.4.1,
please checkout to the [pytorch-0.4.1](https://github.com/open-mmlab/mmdetection/tree/pytorch-0.4.1) branch.

![detected_results](results.jpg)
### Main Features
To adapt to object detection in aerial images, this repo has several unique and new features compared to the original [mmdetection](https://github.com/open-mmlab/mmdetection)
- **Support Oriented Object Detection**
    
    In aerial images, objects are usually annotated by oriented bounding box (OBB).
    To support oriented object detection, we implement OBB Head (OBBRoIHead and OBBDenseHead). 
    Also, we provide functions to transfer mask predictions to OBBs.

- **Cython Bbox Overlaps**
    
    Since one patch image with the size of 1024 &times; 1024 may contain over 1000 instances
     in [DOTA](https://captain-whu.github.io/DOTA/), which make the bbox overlaps memroy consuming.
     To avoid out of GPU memory, we calculate the bbox overlaps in cython. 
     The speed of cython version is close to the GPU version.

- **Rotation Augmentation**
    
    Since there are many orientation variations in aerial images, we implement the online rotation augmentation.
    
- **Rotated RoI Warping**

    Currently, we implement two types of rotated RoI Warping (Rotated RoI Align and Rotated Position Sensitive RoI Align).

- **Large Size Image Inference Demo**
   
## License

This project is released under the [Apache 2.0 license](LICENSE).

## Benchmark and model zoo

We provide a large set of baseline results and trained models available in the [Model zoo](MODEL_ZOO.md).

## Installation


  Please refer to [INSTALL.md](INSTALL.md) for installation.


    
## Get Started

Please see [GETTING_STARTED.md](GETTING_STARTED.md) for the basic usage of mmdetection.

## Contributing

We appreciate all contributions to improve benchmarks for object detection in aerial images. 


## Citing

If you use our [DOTA](https://captain-whu.github.io/DOTA/) dataset, codebase or models in your research, please cite .

```
@inproceedings{xia2018dota,
  title={DOTA: A large-scale dataset for object detection in aerial images},
  author={Xia, Gui-Song and Bai, Xiang and Ding, Jian and Zhu, Zhen and Belongie, Serge and Luo, Jiebo and Datcu, Mihai and Pelillo, Marcello and Zhang, Liangpei},
  booktitle={Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition},
  pages={3974--3983},
  year={2018}
}
```
## Thanks to the Third Party Libs

[Pytorch](https://pytorch.org/)

[mmdetection](https://github.com/open-mmlab/mmdetection)