### Align Deep Features for Oriented Object Detection
Jiaming Han, Jian Ding, Gui-Song Xia.

The repo is based on [mmdetection](https://github.com/open-mmlab/mmdetection).

### Introduction
The past decade has witnessed significant progress on detecting objects in aerial images that are often distributed with large scale variations and arbitrary orientations. However most of existing methods rely on heuristically defined anchors with different scales, angles and aspect ratios and usually suffer from severe misalignment between anchor boxes and axis-aligned convolutional features, which leads to the common inconsistency between the classification score and localization accuracy. To address this issue, we propose a {\em Single-shot Alignment Network} (S$^2$A-Net) consisting of two modules: a Feature Alignment Module (FAM) and an Oriented Detection Module (ODM). The FAM can generate high-quality anchors with an Anchor Refinement Network and adaptively align the convolutional features according to the corresponding anchor boxes with a novel Alignment Convolution. The ODM first adopts active rotating filters to encode the orientation information and then produces orientation-sensitive and orientation-invariant features to alleviate the inconsistency between classification score and localization accuracy. Besides, we further explore the approach to detect objects in large-size images, which leads to a better speed-accuracy trade-off. Extensive experiments demonstrate that our method can achieve state-of-the-art performance on two commonly used aerial objects datasets (\ie, DOTA and HRSC2016) while keeping high efficiency.


## Changelog


## Benchmark and model zoo
|Model          |    Backbone     |    MS  |  Rotate | Lr schd  | Inf time (fps) | box AP | Download|
|:-------------:| :-------------: | :-----:| :-----: | :-----:  | :------------: | :----: | :---------------------------------------------------------------------------------------: |
|RetinaNet      |    R-50-FPN     |   -     |   -    |   1x     |      16.0      |  68.05 |        -        |
|S2ANet         |    R-50-FPN     |   -     |   -    |   1x     |      16.0      |  73.99*|    [model](https://drive.google.com/file/d/19gwDSzCx0uToqI9LyeAg_yXNLgK3sbl_/view?usp=sharing)    |
|S2ANet         |    R-50-FPN     |   ✓     |  ✓     |   1x     |      16.0      |  79.42 |    [model](https://drive.google.com/file/d/1W-JPfoBPHdOxY6KqsD0ZhhLjqNBS7UUN/view?usp=sharing)    |
|S2ANet         |    R-101-FPN    |   ✓     |  ✓     |   1x     |      12.7      |  79.15 |    [model](https://drive.google.com/file/d/1Jkbx-WvKhokEOlWR7WLKxTpH4hDTp-Tb/view?usp=sharing)            |

*Note that we report 74.12 mAP in the paper, however, the pretrained model gets lost. So we re-run it and get 73.99 mAP, which is about 0.1 lower than the original one. 

If you cannot get access to Google Drive, BaiduYun download link can be found [here](https://pan.baidu.com/s/1vsRDUD09RMC1hr9yU7Gviw) with extract code **ABCD**.

## Installation

Please refer to [install.md](docs/INSTALL.md) for installation and dataset preparation.


## Getting Started

Please see [getting_started.md](docs/GETTING_STARTED.md) for the basic usage of MMDetection.



## Citation

```
@article{han2020align
  title = {Align Deep Features for Oriented Object Detection},
  author = {Han, Jiaming and Ding, Jian and Xia, Gui-Song},
  journal = {arXiv preprint},
  year = {2020}
}

@inproceedings{xia2018dota,
  title={DOTA: A large-scale dataset for object detection in aerial images},
  author={Xia, Gui-Song and Bai, Xiang and Ding, Jian and Zhu, Zhen and Belongie, Serge and Luo, Jiebo and Datcu, Mihai and Pelillo, Marcello and Zhang, Liangpei},
  booktitle={Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition},
  pages={3974--3983},
  year={2018}
}

@InProceedings{Ding_2019_CVPR,
  author = {Ding, Jian and Xue, Nan and Long, Yang and Xia, Gui-Song and Lu, Qikai},
  title = {Learning RoI Transformer for Oriented Object Detection in Aerial Images},
  booktitle = {The IEEE Conference on Computer Vision and Pattern Recognition (CVPR)},
  month = {June},
  year = {2019}
}

@article{chen2019mmdetection,
  title={MMDetection: Open mmlab detection toolbox and benchmark},
  author={Chen, Kai and Wang, Jiaqi and Pang, Jiangmiao and Cao, Yuhang and Xiong, Yu and Li, Xiaoxiao and Sun, Shuyang and Feng, Wansen and Liu, Ziwei and Xu, Jiarui and others},
  journal={arXiv preprint arXiv:1906.07155},
  year={2019}
}
```
