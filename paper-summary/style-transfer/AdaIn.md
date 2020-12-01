# AdaIN

| Title | Authors | In One Sentence | Summary | Date | Link | Conference |
| -----  | ------ | --------------- | ------- | ---- | ---- | ---------- |
| Adaptive Style Transfer in Real-Time with Adaptive Instance Normalization | Xun Huang et al. | Introduces an AdaIN layer that allows for arbitraty style transfer in real-time | [Summary](./paper-summary/style-transfer/AdaIN.md) | 30/07/2017 | [Paper](https://arxiv.org/pdf/1703.06868.pdf) | ICCV 2017 | 

## Abstract
- Original style transfer is a slow iterative optimization process
- Some approaches for speedup have been proposed but these only allow for a fixed set of styles
- AdaIN layer proposed: aligns the mean and variance of content and style features

## Introduction
- We want speed **and** style flexibility: AdaIN, which is based on Instance Normalization layer which has proven very effective in feed-forward style transfer
- Interpretation: instance normalization works because it performs style normalization

## Background
- Batch Normalization has been known to alleviate domain shifts, making the AdaIN layer even more intuitive
- Instance Normalization has been known to work better for style transfer
- Conditional Instance Normalization has shown that when applied to styles, same conv parameters can generate images in completely different styles -> However, amount of params scales with styles

## Interpreting Instance Normalization
- They argue that instance normalization can be seen as a form of style transformation

## Adaptive Instance Normalization
- AdaIN receives content input x and style input y: normalizes x and then scales by the variance of y and adds mean of y
- AdaIN has **no learnable params**

## Results
- Degree if style transfer is a single param, style interpolation is incredibly easy too
 

