# Partial-Person-ReID
******************************************************************************************************************

**The source code**: Spatial Feature Reconstruction with Pyramid Pooling for Partial Person Re-identification 
CVPR18: [Deep Spatial Feature Reconstruction for Partial Person Re-identification: Alignment-free Approach](http://openaccess.thecvf.com/content_cvpr_2018/papers/He_Deep_Spatial_Feature_CVPR_2018_paper.pdf), Arxiv18 

The project provides the training and testing code for partial person re-id, using [Pytorch](https://pytorch.org/)

## Instllation
*****************************************************************************************************************
It's recommended that you create and enter a python virtual environment, if versions of the packages required here conflict with yours.

Other packages are specified in `requirements.txt`

## Daset Preparation
Inspired by Houjing Huang's [person-reid-triplet-loss-baseline](https://github.com/huanghoujing/person-reid-triplet-loss-baseline) project, you can follow his guidance.

## Experiment Setting:
1. Backbone: ResNet-50, `stride = 1` in the last conv block.
2. Input image size: `384 & times 192`

## Person Re-identification
### Result on Market1501
```
python script/experiment/train.py \
--dataset market1501 \
--partial_dataset others\
--Spatial_train False \
--total_epochs 400 
```
   | Method | Rank-1 (Single query) | mAP | Rank-1 (Multi query)| mAP |
| - | :-: | -: |  :-: | -: | 
| Baseline | 88.18| 73.85 | 92.25 | 80.96|
| SFR | 93.04 | 81.02 | 94.84 | 85.47 |

### Result on CUHK03
```
python script/experiment/train.py \
--dataset cuhk03 \
--partial_dataset others\
--Spatial_train False \
--total_epochs 400 
```
   | Method | Rank-1 (Labeled) | mAP | Rank-1 (Detected)| mAP |
| - | :-: | -: |  :-: | -: | 
| Baseline | 62.14| 58.47 | 92.25 | 54.24|
| SFR | 67.29 |61.47 | 63.86 | 58.97 |

### Result on Duke
```
python script/experiment/train.py \
--dataset duke \
--partial_dataset others\
--Spatial_train False \
--total_epochs 400 
```
   | Method | Rank-1 (Labeled) | mAP|
| - | :-: | -: | 
| Baseline | 80.48| 64.80 |
| SFR | 84.83 |71.24 | 
