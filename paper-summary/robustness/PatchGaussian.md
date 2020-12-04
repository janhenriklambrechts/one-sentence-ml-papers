## Patch Gaussian

| Title | Authors | In One Sentence | Summary | Date | Link | Conference |
| -----  | ------ | --------------- | ------- | ---- | ---- | ---------- |
| Improving Robustness Without Sacrificing Accuracy with Patch Gaussian Augmentation | Raphel Gontijo Lopes et al. | Combining Cutout and Gaussian noise in a single data augmentation scheme improves robustness while not incurring accuracy drop.  | [Summary](./paper-summary/robustness/PatchGaussian.md) | 06/06/2019 | [Paper](https://arxiv.org/pdf/1906.02611.pdf) | ICML 2019 Workshop | 

## Abstract
- Cutout improves clean accuracy but not robustness
- Gaussian Noise improves robustness yet kills clean accuracy
- Patch Gaussian improves robustness yet does not incur the clean accuracy drop

## Introduction
- Data augmentation is an attractive approach to solve robustness and has not received enough attention

## Method
- Patch Gaussian: Gaussian Noise applied to pixels in a square patch
- SOTA in CIFAR-10 C and ImageNet-C
- Patch Gaussian improves performance on Fog corruption even though normal gaussian would hurt accuracy 
- label smoothing hurts Corruption robustness

## Discussion
- Gaussian encourages the model to learn a low pass filter of the inputs, which helps versus hi-freq inputs. However, throwing this valuable inputs away can hurt clean accuracy
- Cutout encourages use of hi-freq, helping generalizaion
- Patch Gaussian allows hi-freq information but encourages lower test error sensitivity at hi-freq
