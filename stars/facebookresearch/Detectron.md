---
project: Detectron
stars: 26385
description: FAIR's research platform for object detection research, implementing popular algorithms like Mask R-CNN and RetinaNet.
url: https://github.com/facebookresearch/Detectron
---

**Detectron is deprecated. Please see detectron2, a ground-up rewrite of Detectron in PyTorch.**

Detectron
=========

Detectron is Facebook AI Research's software system that implements state-of-the-art object detection algorithms, including Mask R-CNN. It is written in Python and powered by the Caffe2 deep learning framework.

At FAIR, Detectron has enabled numerous research projects, including: Feature Pyramid Networks for Object Detection, Mask R-CNN, Detecting and Recognizing Human-Object Interactions, Focal Loss for Dense Object Detection, Non-local Neural Networks, Learning to Segment Every Thing, Data Distillation: Towards Omni-Supervised Learning, DensePose: Dense Human Pose Estimation In The Wild, and Group Normalization.

Example Mask R-CNN output.

Introduction
------------

The goal of Detectron is to provide a high-quality, high-performance codebase for object detection _research_. It is designed to be flexible in order to support rapid implementation and evaluation of novel research. Detectron includes implementations of the following object detection algorithms:

-   Mask R-CNN -- _Marr Prize at ICCV 2017_
-   RetinaNet -- _Best Student Paper Award at ICCV 2017_
-   Faster R-CNN
-   RPN
-   Fast R-CNN
-   R-FCN

using the following backbone network architectures:

-   ResNeXt{50,101,152}
-   ResNet{50,101,152}
-   Feature Pyramid Networks (with ResNet/ResNeXt)
-   VGG16

Additional backbone architectures may be easily implemented. For more details about these models, please see References below.

Update
------

-   4/2018: Support Group Normalization - see `GN/README.md`

License
-------

Detectron is released under the Apache 2.0 license. See the NOTICE file for additional details.

Citing Detectron
----------------

If you use Detectron in your research or wish to refer to the baseline results published in the Model Zoo, please use the following BibTeX entry.

```
@misc{Detectron2018,
  author =       {Ross Girshick and Ilija Radosavovic and Georgia Gkioxari and
                  Piotr Doll\'{a}r and Kaiming He},
  title =        {Detectron},
  howpublished = {\url{https://github.com/facebookresearch/detectron}},
  year =         {2018}
}
```

Model Zoo and Baselines
-----------------------

We provide a large set of baseline results and trained models available for download in the Detectron Model Zoo.

Installation
------------

Please find installation instructions for Caffe2 and Detectron in `INSTALL.md`.

Quick Start: Using Detectron
----------------------------

After installation, please see `GETTING_STARTED.md` for brief tutorials covering inference and training with Detectron.

Getting Help
------------

To start, please check the troubleshooting section of our installation instructions as well as our FAQ. If you couldn't find help there, try searching our GitHub issues. We intend the issues page to be a forum in which the community collectively troubleshoots problems.

If bugs are found, **we appreciate pull requests** (including adding Q&A's to `FAQ.md` and improving our installation instructions and troubleshooting documents). Please see CONTRIBUTING.md for more information about contributing to Detectron.

References
----------

-   Data Distillation: Towards Omni-Supervised Learning. Ilija Radosavovic, Piotr Dollár, Ross Girshick, Georgia Gkioxari, and Kaiming He. Tech report, arXiv, Dec. 2017.
-   Learning to Segment Every Thing. Ronghang Hu, Piotr Dollár, Kaiming He, Trevor Darrell, and Ross Girshick. Tech report, arXiv, Nov. 2017.
-   Non-Local Neural Networks. Xiaolong Wang, Ross Girshick, Abhinav Gupta, and Kaiming He. Tech report, arXiv, Nov. 2017.
-   Mask R-CNN. Kaiming He, Georgia Gkioxari, Piotr Dollár, and Ross Girshick. IEEE International Conference on Computer Vision (ICCV), 2017.
-   Focal Loss for Dense Object Detection. Tsung-Yi Lin, Priya Goyal, Ross Girshick, Kaiming He, and Piotr Dollár. IEEE International Conference on Computer Vision (ICCV), 2017.
-   Accurate, Large Minibatch SGD: Training ImageNet in 1 Hour. Priya Goyal, Piotr Dollár, Ross Girshick, Pieter Noordhuis, Lukasz Wesolowski, Aapo Kyrola, Andrew Tulloch, Yangqing Jia, and Kaiming He. Tech report, arXiv, June 2017.
-   Detecting and Recognizing Human-Object Interactions. Georgia Gkioxari, Ross Girshick, Piotr Dollár, and Kaiming He. Tech report, arXiv, Apr. 2017.
-   Feature Pyramid Networks for Object Detection. Tsung-Yi Lin, Piotr Dollár, Ross Girshick, Kaiming He, Bharath Hariharan, and Serge Belongie. IEEE Conference on Computer Vision and Pattern Recognition (CVPR), 2017.
-   Aggregated Residual Transformations for Deep Neural Networks. Saining Xie, Ross Girshick, Piotr Dollár, Zhuowen Tu, and Kaiming He. IEEE Conference on Computer Vision and Pattern Recognition (CVPR), 2017.
-   R-FCN: Object Detection via Region-based Fully Convolutional Networks. Jifeng Dai, Yi Li, Kaiming He, and Jian Sun. Conference on Neural Information Processing Systems (NIPS), 2016.
-   Deep Residual Learning for Image Recognition. Kaiming He, Xiangyu Zhang, Shaoqing Ren, and Jian Sun. IEEE Conference on Computer Vision and Pattern Recognition (CVPR), 2016.
-   Faster R-CNN: Towards Real-Time Object Detection with Region Proposal Networks Shaoqing Ren, Kaiming He, Ross Girshick, and Jian Sun. Conference on Neural Information Processing Systems (NIPS), 2015.
-   Fast R-CNN. Ross Girshick. IEEE International Conference on Computer Vision (ICCV), 2015.
