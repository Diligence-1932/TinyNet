<div align="center">
<h1> TinyDF: Tiny and Effective Model for Deepfake Detection </h1>
</div>

## 🎈 News

- [2024.11.10] Training and inference code released

## 🚀 Introduction

Deepfake detection aims to identify fake videos generated by deep learning techniques. Although deepfake detection methods have achieved remarkable progress, several challenges remain: (1) The existing detection methods are difficult to achieve a good trade-off between performance and model complexity. (2) Existing methods often introduce significant redundancy when modeling the relationship between local and global features. (3) Achieving generalization in deepfake detection remains a major challenge, as performance tends to degrade significantly when there is a domain mismatch between the training and testing datasets. To address the above challenges, we propose a novel lightweight framework, Tiny Deepfake Detection (TinyDF), which has an extremely small number of parameters and achieves exceptional performance. Specifically, we propose a Pyramid Atrous Aggregation (PAA) module to address the significant redundancy caused by the spatial inconsistency between global and local features. This module enables multiperspective perception of global and local features and maps them into a unified feature space for detailed interaction. Secondly, we propose a low-cost but highly efficient fusion module, Shuffle Fusion Mixer (SFM), which enhances feature interaction through multi-resolution integration, thereby improving cross-dataset generalization. We explore the first application of the Kolmogorov-Arnold idea in deep forgery detection, which significantly improves the detection performance through powerful nonlinear expression. Extensive experiments demonstrate that TinyDF outperforms existing methods in both generalization and accuracy. Notably, TinyDF requires only 5.38M parameters and 0.59G FLOPs. If the paper is accepted we will publish the code.

## 📻 Overview

<div align="center">
<img width="800" alt="image" src="asserts/TinyNet.png?raw=true">
</div>


The overall architecture of tiny deepfake detection (TinyDF). It consists of four main components: TinyNet, Pyramid Atrous Aggregation (PAA), Shuffle Fusion Mixer (SFM) and a classification module containing KAN.


<div align="center">
    <img width="400" alt="image" src="asserts/introduction.png?raw=true">
</div>


Compared with the existing methods in terms of model parameters, calculation cost and performance. A larger circular area indicates a larger FLOPs. Our model achieves SOTA performance at a very low computational cost and parameters.

## 📆 TODO

- [x] Release code

## 🎮 Getting Started

### 1. Install Environment

```
conda create -n TinyDF python=3.8
conda activate TinyDF
pip install -r requirements.txt
```

### 2. Prepare Datasets

- Download datasets: FF++(c23) from this [link](github.com/ondyari/FaceForensics), DFDC from this [link](deepfakedetectionchallenge.ai), and DFR from this [link](https://github.com/EndlessSora/DeeperForensics-1.0), CelebDF-v2 from this[link](http://www.cs.albany.edu/˜lsw/celeb-deepfakeforensics.html), and WDF from this [link](https://github.com/deepfakeinthewild/deepfake-in-the-wild).
- Folder organization: put FF++(c23) datasets into ./data/FF++(c23) folder, DFDC datasets into ./data/DFDC folder, and DFR datasets into ./data/DFR folder, CelebDF-v2 datasets into ./data/CelebDF-v2 folder, and WDF datasets into ./data/WDF folder.


### 3. Train the TinyDF

```
python train.py --datasets
training records is saved to ./log folder
pre-training file is saved to ./checkpoints
concrete information see .train.py, please
```

### 3. Test the TinyDF

```
python test.py --datasets
testing records is saved to ./log folder
testing results are saved to ./Test
concrete information see .test.py, please
```


## 🎫 License

The content of this project itself is licensed under [LICENSE](LICENSE).



