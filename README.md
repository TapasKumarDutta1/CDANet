## CDANET

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

This repository contains the Tensorflow implementation of our paper "CDANET: CHANNEL SPLIT DUAL ATTENTION BASED CNN FOR BRAIN TUMOR
CLASSIFICATION IN MR IMAGES"

## Requirements
Python 3.7.13 <br />
<br />
Numpy 1.21.6 <br />
<br />
Tensorflow 2.8.0 <br />
<br />
Opencv-python 4.1.2 <br />
<br />
Pandas 1.3.5 <br />
<br />
h5py 3.1.0 <br />
<br />
Imgaug 0.2.9 <br />
<br />


## Useage
- Download the figshare dataset, extract the zip files and put them along with the cvind.mat in the kaggle/input folder.

- To train the model run the following code: python train.py. Note that parameters and paths should be set beforehand


## BraTS2020 
BraTS 2020 dataset contains two types of tumors: High-Grade Glioma(HGG) and Low-Grade Glioma(LGG). It consists of 293 HGG and 76 LGG 3D MR images. We used a stratified five fold cross validation scheme and trained the entire model in an end to end manner.
 
## Results

### Table 1. Fold-wise Classification Results (in %) of our CDANet on Figshare dataset
Fold|Sensitivity|Specificity|F1-score|Accuracy
---|---|---|---|---
Fold1|96.87|98.10|97.40|97.78
Fold2|96.59|97.40|96.89|96.61
Fold3|95.64|96.54|96.00|96.32
Fold4|97.03|96.00|96.49|97.29
Fold5|94.58|94.35|94.33|95.02
Average|96.14|96.47|96.22|96.60

### Table 2. Comparison of different parts of CSDA block
Model|Attention Type|Sensitivity|Specificity|F1-Score|Accuracy
---|---|---|---|---|---
Densenet121|Ours|96.14|96.47|96.22|96.60
Densenet121|PAB|95.72|95.58|95.43|95.95
Densenet121|CAB|96.01|95.86|95.55|96.33
Densenet121|No Channel Split|95.83|95.66|95.68|96.21
Densenet121|None|95.34|95.28|95.09|95.88

### Table 3. Comparison with existing CNN based classification methods on the same dataset
Author|Method|Accuracy(%)
---|---|---
Paul et al.|Custom CNN|90.26
Asfhar et al.|CapsNet|86.56
Swati et al.|VGG19 with BFT|94.82
Ghassemi et al.|GAN with custom CNN|93.01
Bodapati et al.|Two-Channel DNN| 95.23
Bodapati et al.|MSENet| 95.37
Abirami and Venkatesan| BCFA based GAN| 95.52
Ours|CDANet|96.60

### Table 4. Fold-wise Classification Results (in %) of our CDANet on BraTS 2020 dataset
Fold|Sensitivity|Specificity|F1 Score|Accuracy
---|---|---|---|---
Fold1|88.31|80.00|83.94|82.69
Fold2|100|100|100|100
Fold3|100|100|100|100
Fold4|100|100|100|100
Fold5|100|100|100|100
Avg.|97.66|96.00|96.78|96.53

### Table 5. Model performance on reduced training data
Number of training folds used|Accuracy(in %)
---|---
4|96.60
3|95.81
2|95.60

## Citation

```markdown
@INPROCEEDINGS{9897799,
  author={Kumar Dutta, Tapas and Ranjan Nayak, Deepak},
  booktitle={2022 IEEE International Conference on Image Processing (ICIP)}, 
  title={CDANet: Channel Split Dual Attention Based CNN for Brain Tumor Classification In Mr Images}, 
  year={2022},
  volume={},
  number={},
  pages={4208-4212},
  doi={10.1109/ICIP46576.2022.9897799}}
