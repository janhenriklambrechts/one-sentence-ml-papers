# RandAugment
| Title | Authors | In One Sentence | Summary | Date | Link | Conference |
| -----  | ------ | --------------- | ------- | ---- | ---- | ---------- |
| RandAugment: Practical Automated Data Augmentation with a Reduced Search Space | Ekin D. Cubuk, Barret Zoph et al. | Searching for a single distortion magnitude can do as well or improve previous automated augmentation stratgies  | [Summary](./paper-summary/data-augmentation/RandAugment.md) | 11/04/2019 | [Paper](https://proceedings.neurips.cc/paper/2020/file/d85b63ef0ccb114d0a3bb7b7d808028f-Paper.pdf) | NeurIPS 2020 | 

## Abstract 
- SOTA of image classification and OD is driven by data augmentation but these strategies use a large search space
- It is sufficient to search for a single param taht jointly controls all operations

## Introduction
- Automated ML has led to improved classification, object detection, model robustness and semi-supervised learning
- Obstacle is the large search phase, often alleviated with a smaller proxy task
- We demonstrate that these proxy tasks do not (always) lead to the optimal setup
- Actually constraining the search process to a single magnitude and probability works great!

## Related Work
- Relevant Augmentation Strategies: MixUp, Smart Augmentation, GANs

## Automated Data Augmentation without a proxy task
- Replace probability p with always selecting a procedure k \in K with uniform probabilitu 1/len(K)
- Replace magnitude with a single param that scales from 1 to 10
- Simple grid search works!

## Discussion
- Open Question is how one may choose the set of transformations ofor a particular task
