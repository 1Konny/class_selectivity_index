### Overview
<p align="center">
<img src=assets/results.png>
</p>
<br>
Very simple replication of the Figure A2 (b) shown in the paper, On the importance of single directions for generalization(Morcos et al, ICLR 2018), which demonstrates that class selectivity increases with depth.
The original paper used resnet-50 but this code uses vgg11. Please refer to the original paper for the details.

This code is tested on NVIDIA GTX 1080 Ti(11GB), i7-8700, 32GB RAM, and will occupy ~29GB if save_outputs is set to True.

### Dependencies
```
python 3.6.4
pytorch 0.4.0
tqdm
```

### File Structure
```
.
└── README.md
├── figure.ipynb
├── assets
    └── results.png
├── data
    └── ILSVRC2012_img_val
        └── n01440764
        ├── n01443537
        ├── n01484850
        ├── ...
        └── n15075141
├── outputs
    └── vgg11
        ├── classifier_1_activations.pth
        ├── classifier_1_selectivity_results.pth
        ├── ...
        └── features_9_selectivity_results.pth
└── ...
```

### Dataset Setting
```
cd data
wget http://www.image-net.org/challenges/LSVRC/2012/nnoupb/ILSVRC2012_img_val.tar
mkdir ILSVRC2012_img_val
mv ILSVRC2012_img_val.tar ILSVRC2012_img_val
mv valprep.sh ILSVRC2012_img_val
cd ILSVRC2012_img_val
tar -xvf ILSVRC2012_img_val.tar
sh valprep.sh
```

### Reference
1. On the importance of single directions for generalization, Morcos et al, ICLR, 2018
