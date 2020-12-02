# AutoAugment

| Title | Authors | In One Sentence | Summary | Date | Link | Conference |
| -----  | ------ | --------------- | ------- | ---- | ---- | ---------- |
| AutoAugment: Learning Augmentation Strategies from Data | Ekin D. Cubuk et al. | Meta-learning data augmentation for new SOTA on classification | [Summary](./paper-summary/data-augmentation/AutoAugment.md) | 11/04/2019 | [Paper](https://arxiv.org/pdf/1805.09501.pdf) | ArXiv | 

## Abstract
- Current data augmentation policies are manually designed instead of learned
- AutoAugment chooses a random subpolicy consisting of an image processing function - probability and magnitude
- Search algo that yields the highest validation accuracy on a target dataset
- Augmentation policies transfer from ImageNet to other datasets


## Introduction
- We want to learn certain invariances (f.e. flipping, translating, etc.), we can do this by 1) data aug or 2) network architecture (f.e. conv filters), better data aug is a lot easier
- Image augmentation strategies can be good for one dataset but not for the other (f.e. HorizontalFlip is good for CIFAR, bad for MNIST)
- They propose a Reinforcement Learning approach for search, if this is too expensive just use a pretrained data aug strategy -> New version of transfer learning

## Related Work
- Reinforcement learning is very common in Architecture search yet not used in data aug setting

## AutoAugment: Searching for best Augmentation policies Directly on the dataset of interest
- Two components: 1) Search algo and 2) search space; Data Augmentation Policy S and validation accuracy R
- Every policy consists of 5 sub-policies and each subpolicy consists of two image operations in sequence + probability P and magnitude M
- This search strategy could definitely be improved

## Experiments and Results
- Actually they first do standard preprocessing and only apply these extra processes afterwards
- Color is very succesful apparently, random policies with AutoAugment lead to performance increase as well

