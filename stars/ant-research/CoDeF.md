---
project: CoDeF
stars: 4869
description: [CVPR'24 Highlight] Official PyTorch implementation of CoDeF: Content Deformation Fields for Temporally Consistent Video Processing
url: https://github.com/ant-research/CoDeF
---

CoDeF: Content Deformation Fields for Temporally Consistent Video Processing
============================================================================

Hao Ouyang\*, Qiuyu Wang\*, Yuxi Xiao\*, Qingyan Bai, Juntao Zhang, Kecheng Zheng, Xiaowei Zhou, Qifeng Chen†, Yujun Shen† (\*equal contribution, †corresponding author)

**CVPR 2024 Highlight**

#### Project Page | Paper | High-Res Translation Demo | Colab

Requirements
------------

The codebase is tested on

-   Ubuntu 20.04
-   Python 3.10
-   PyTorch 2.0.0
-   PyTorch Lightning 2.0.2
-   1 NVIDIA GPU (RTX A6000) with CUDA version 11.7. (Other GPUs are also suitable, and 10GB GPU memory is sufficient to run our code.)

To use video visualizer, please install `ffmpeg` via

sudo apt-get install ffmpeg

For additional Python libraries, please install with

pip install -r requirements.txt

Our code also depends on tiny-cuda-nn. See this repository for Pytorch extension install instructions.

Data
----

### Provided data

We have provided some videos here for quick test. Please download and unzip the data and put them in the root directory. More videos can be downloaded here.

### Customize your own data

We segement video sequences using SAM-Track. Once you obtain the mask files, place them in the folder `all_sequences/{YOUR_SEQUENCE_NAME}/{YOUR_SEQUENCE_NAME}_masks`. Next, execute the following command:

cd data\_preprocessing
python preproc\_mask.py

We extract optical flows of video sequences using RAFT. To get started, please follow the instructions provided here to download their pretrained model. Once downloaded, place the model in the `data_preprocessing/RAFT/models` folder. After that, you can execute the following command:

cd data\_preprocessing/RAFT
./run\_raft.sh

Remember to update the sequence name and root directory in both `data_preprocessing/preproc_mask.py` and `data_preprocessing/RAFT/run_raft.sh` accordingly.

After obtaining the files, please organize your own data as follows:

```
CoDeF
│
└─── all_sequences
    │
    └─── NAME1
           └─ NAME1
           └─ NAME1_masks_0 (optional)
           └─ NAME1_masks_1 (optional)
           └─ NAME1_flow (optional)
           └─ NAME1_flow_confidence (optional)
    │
    └─── NAME2
           └─ NAME2
           └─ NAME2_masks_0 (optional)
           └─ NAME2_masks_1 (optional)
           └─ NAME2_flow (optional)
           └─ NAME2_flow_confidence (optional)
    │
    └─── ...
```

Pretrained checkpoints
----------------------

You can download checkpoints pre-trained on the provided videos via

Sequence Name

Config

Download

OpenXLab

beauty\_0

configs/beauty\_0/base.yaml

Google drive link

beauty\_1

configs/beauty\_1/base.yaml

Google drive link

white\_smoke

configs/white\_smoke/base.yaml

Google drive link

lemon\_hit

configs/lemon\_hit/base.yaml

Google drive link

scene\_0

configs/scene\_0/base.yaml

Google drive link

And organize files as follows

```
CoDeF
│
└─── ckpts/all_sequences
    │
    └─── NAME1
        │
        └─── EXP_NAME (base)
            │
            └─── NAME1.ckpt
    │
    └─── NAME2
        │
        └─── EXP_NAME (base)
            │
            └─── NAME2.ckpt
    |
    └─── ...
```

Train a new model
-----------------

./scripts/train\_multi.sh

where

-   `GPU`: Decide which GPU to train on;
-   `NAME`: Name of the video sequence;
-   `EXP_NAME`: Name of the experiment;
-   `ROOT_DIRECTORY`: Directory of the input video sequence;
-   `MODEL_SAVE_PATH`: Path to save the checkpoints;
-   `LOG_SAVE_PATH`: Path to save the logs;
-   `MASK_DIRECTORY`: Directory of the preprocessed masks (optional);
-   `FLOW_DIRECTORY`: Directory of the preprocessed optical flows (optional);

Please check configuration files in `configs/`, and you can always add your own model config.

Test reconstruction
-------------------

./scripts/test\_multi.sh

After running the script, the reconstructed videos can be found in `results/all_sequences/{NAME}/{EXP_NAME}`, along with the canonical image.

Test video translation
----------------------

After obtaining the canonical image through this step, use your preferred text prompts to transfer it using ControlNet. Once you have the transferred canonical image, place it in `all_sequences/${NAME}/${EXP_NAME}_control` (i.e. `CANONICAL_DIR` in `scripts/test_canonical.sh`).

Then run

./scripts/test\_canonical.sh

The transferred results can be seen in `results/all_sequences/{NAME}/{EXP_NAME}_transformed`.

_Note_: The `canonical_wh` option in the configuration file should be set with caution, usually a little larger than `img_wh`, as it determines the field of view of the canonical image.

### BibTeX

@article{ouyang2023codef,
      title\={CoDeF: Content Deformation Fields for Temporally Consistent Video Processing},
      author\={Hao Ouyang and Qiuyu Wang and Yuxi Xiao and Qingyan Bai and Juntao Zhang and Kecheng Zheng and Xiaowei Zhou and Qifeng Chen and Yujun Shen},
      journal\={arXiv preprint arXiv:2308.07926},
      year\={2023}
}

### Acknowledgements

We thank camenduru for providing the colab demo.
