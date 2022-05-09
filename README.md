# Normal-Aware-MVSNet

This repository contains the code of course project for CMU-16889 (advised by Shubham Tulsiani).

[**NA-MVSNet--A Normal-Aware MVSNet with View-Consistency for Depth Estimation.**](https://github.com/dijingzhang/NA-MVSNet/blob/main/NA-MVSNet.pdf)

[Dijing Zhang*](https://github.com/dijingzhang)
[Chenhao Yang*](https://github.com/afiretony)

## Datasets

Datasets can be generated by data_io.py and we have preprocessed the low-resolution dataset from Eth3d (containing the image, depth and normal maps). You can download the [low-resolution datasets](https://drive.google.com/file/d/1NeWTiVFUkP1IaL9qxazTA1LVqk1w0_lC/view?usp=sharing) and [high-resolution datasets](https://cmu.box.com/s/mk4w3tspxrn49r2fzbr3x98pi3g2v60f)

### Normal Map Generation
Normal Map is genertaed by the idea from [this paper](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=7335535) and this normal is normalized to be unit.


## Model

Model architecture is shown here:
<center><img src="https://github.com/16889-team/Normal-Aware-MVSNet/blob/main/images/model.png" alt=""></center>


## Train

Currently, we only test the low-resolution datasets and batch_size is set to be 16 due to the lack of computer resources.

You can do the training in your local machine with:
```bash
python train.py --mode train/val --batch_size 16 --alpha [need to tune] --beta [need to tune] --gamma [need to tune]
```

Or use colab with [this](https://github.com/16889-team/Normal-Aware-MVSNet/blob/main/na_mvsnet_training.ipynb) (Remember to upload the datasets to your gdrive)

You can see the training result in checkpoints/log. (With three different parameter-settings)

## Acknowledgement
This project heavily relies codes from [MVSNet-pytorch](https://github.com/xy-guo/MVSNet_pytorch) and insipred by [NAS](https://github.com/udaykusupati/Normal-Assisted-Stereo) and we thank the authors for releasing their code.

We also thank Shubham Tulsiani for suggestions and guidance.
