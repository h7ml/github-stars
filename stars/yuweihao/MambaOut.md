---
project: MambaOut
stars: 2498
description: MambaOut: Do We Really Need Mamba for Vision? (CVPR 2025)
url: https://github.com/yuweihao/MambaOut
---

MambaOut: Do We Really Need Mamba for Vision? (CVPR 2025)
=========================================================

_In memory of Kobe Bryant_

> "What can I say, Mamba out." — _Kobe Bryant, NBA farewell speech, 2016_

  
Image credit: https://www.ebay.ca/itm/264973452480

This is a PyTorch implementation of MambaOut proposed by our paper "MambaOut: Do We Really Need Mamba for Vision?".

Updates
-------

-   22 October 2024: Huge thanks to Ross @rwightman for integrating MambaOut into pytorch-image-models (timm) and developing the mambaout\_rw model series. The impressive mambaout\_base\_plus\_rw model (102M params), pretrained solely on ImageNet-12k, "_is matching or passing accuracy levels of ImageNet-22k pretrained ConvNeXt-Large (~200M params), it's not far from the best 22k trained ViT-Large (DeiT-III, ~300M params)_". Please see Ross's article for more details.
    
-   20 May 2024: As suggested by Issue #5, we release **MambaOut-Kobe** model version with **24** Gated CNN blocks, achieving **8**0.0% accuracy on ImageNet. MambaOut-Kobe outperforms ViT-S by 0.2% accuracy with only 41% parameters and 33% FLOPs. See Models.
    
-   18 May 2024: Add a tutorial on counting Transformer FLOPs (Equation 6 in the paper).
    

* * *

Figure 1: (a) Architecture of Gated CNN and Mamba blocks (omitting Normalization and shortcut). The Mamba block extends the Gated CNN with an additional state space model (SSM). As will be conceptually discussed in Section 3, SSM is not necessary for image classification on ImageNet. To empirically verify this claim, we stack Gated CNN blocks to build a series of models named MambaOut.(b) MambaOut outperforms visual Mamba models, e.g., Vision Mamhba, VMamba and PlainMamba, on ImageNet image classification.

  

Figure 2: The mechanism illustration of causal attention and RNN-like models from memory perspective, where $x\_i$ denotes the input token of $i$-th step. (a) Causal attention stores all previous tokens' keys $k$ and values $v$ as memory. The memory is updated by continuously adding the current token's key and value, so the memory is lossless, but the downside is that the computational complexity of integrating old memory and current tokens increases as the sequence lengthens. Therefore attention can effectively manage short sequences but may encounter difficulties with longer ones. (b) In contrast, RNN-like models compress previous tokens into fixed-size hidden state $h$, which serves as the memory. This fixed size means that RNN memory is inherently lossy, which cannot directly compete with the lossless memory capacity of attention models. Nonetheless, **RNN-like models can demonstrate distinct advantages in processing long sequences, as the complexity of merging old memory with current input remains constant, regardless of sequence length.**

  

Figure 3: (a) Two modes of token mixing. For a total of $T$ tokens, the fully-visible mode allows token $t$ to aggregate inputs from all tokens, i.e., $ \\left{ x\_i \\right}_{i=1}^{T} $, to compute its output $y\_t$. In contrast, the causal mode restricts token $t$ to only aggregate inputs from preceding and current tokens $ \\left{ x\_i \\right}_{i=1}^{t} $. By default, attention operates in fully-visible mode but can be adjusted to causal mode with causal attention masks. RNN-like models, such as Mamba's SSM, inherently operate in causal mode due to their recurrent nature. (b) **We modify the ViT's attention from fully-visible to causal mode and observe performance drop on ImageNet, which indicates causal mixing is unnecessary for understanding tasks.**

Requirements
------------

PyTorch and timm 0.6.11 (`pip install timm==0.6.11`).

Data preparation: ImageNet with the following folder structure, you can extract ImageNet by this script.

```
│imagenet/
├──train/
│  ├── n01440764
│  │   ├── n01440764_10026.JPEG
│  │   ├── n01440764_10027.JPEG
│  │   ├── ......
│  ├── ......
├──val/
│  ├── n01440764
│  │   ├── ILSVRC2012_val_00000293.JPEG
│  │   ├── ILSVRC2012_val_00002138.JPEG
│  │   ├── ......
│  ├── ......
```

Models
------

### MambaOut trained on ImageNet

Model

Resolution

Params

MACs

Top1 Acc

Log

mambaout\_femto

224

7.3M

1.2G

78.9

log

mambaout\_kobe\*

224

9.1M

1.5G

80.0

log

mambaout\_tiny

224

26.5M

4.5G

82.7

log

mambaout\_small

224

48.5M

9.0G

84.1

log

mambaout\_base

224

84.8M

15.8G

84.2

log

\* Kobe Memorial Version with 24 Gated CNN blocks.

#### Usage

We also provide a Colab notebook which runs the steps to perform inference with MambaOut: .

Gradio demo
-----------

A web demo is shown at . You can also easily run gradio demo locally. Besides PyTorch and timm==0.6.11, please install gradio by `pip install gradio`, then run

python gradio\_demo/app.py

Validation
----------

To evaluate models, run:

MODEL=mambaout\_tiny
python3 validate.py /path/to/imagenet  --model $MODEL -b 128 \\
  --pretrained

Train
-----

We use batch size of 4096 by default and we show how to train models with 8 GPUs. For multi-node training, adjust `--grad-accum-steps` according to your situations.

DATA\_PATH=/path/to/imagenet
CODE\_PATH=/path/to/code/MambaOut # modify code path here

ALL\_BATCH\_SIZE=4096
NUM\_GPU=8
GRAD\_ACCUM\_STEPS=4 # Adjust according to your GPU numbers and memory size.
let BATCH\_SIZE=ALL\_BATCH\_SIZE/NUM\_GPU/GRAD\_ACCUM\_STEPS


MODEL=mambaout\_tiny 
DROP\_PATH=0.2

cd $CODE\_PATH && sh distributed\_train.sh $NUM\_GPU $DATA\_PATH \\
--model $MODEL --opt adamw --lr 4e-3 --warmup-epochs 20 \\
-b $BATCH\_SIZE --grad-accum-steps $GRAD\_ACCUM\_STEPS \\
--drop-path $DROP\_PATH # --native-amp # can also use --native-amp or --amp to acclerate training

Training scripts of other models are shown in scripts.

Tutorial on counting Transformer FLOPs
--------------------------------------

This tutorial shows how to count Transformer FLOPs (Equation 6 in the paper). Welcome feedback, and I will continually improve it.

Bibtex
------

```
@inproceedings{yu2025mambaout,
  title={MambaOut: Do We Really Need Mamba for Vision?},
  author={Yu, Weihao and Wang, Xinchao},
  booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition},
  year={2025}
}
```

Acknowledgment
--------------

Weihao was partly supported by Snap Research Fellowship, Google TPU Research Cloud (TRC), and Google Cloud Research Credits program. We thank Dongze Lian, Qiuhong Shen, Xingyi Yang, and Gongfan Fang for valuable discussions.

Our implementation is based on pytorch-image-models, poolformer, ConvNeXt, metaformer and inceptionnext.
