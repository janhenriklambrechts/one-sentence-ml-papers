## RepVGG: Making VGG-style ConvNets Great Again

| Title | Authors | In One Sentence | Summary | Date | Link | Conference |
| -----  | ------ | --------------- | ------- | ---- | ---- | ---------- |
| RepVGG: Making VGG-style ConvNets Great Again | Xiaohan Ding et al. | Decoupling of training-time and inference-time architecture can lead to inference speedup of 83% over ResNet-50 while reaching 80+% on ImageNet | [Summary](./paper-summary/vision-architectures/RepVGG.md) | 11/01/2021 | [Paper](https://arxiv.org/pdf/2101.03697v1.pdf)| ArXiv | 

### Abstract
- VGG-like inference model proposed that only consists of 3x3 Conv and ReLUs - by structural re-parameterization
- During Training Rep-VGG has a multi-branch model, yet during test it looks like VGG

### Introduction
- residuals (ResNet) and branch-concatenation (Inception) slow down inference and reduce memory utilization -- depthwise Conv (Xception and MobileNets) and channel shuffle (Shufflenet) increase memory access cost and lack support on many devices: therefore FLOPS is not always speed --> This is why VGG and ResNet are still widely used despite being old
- observation: training-time multibranch has advantages and test-time simple feedforward has advantages
- After training we can do some simple linear algebra: identity branch can be seen as 1x1 conv and 1x1 can be seens as 3x3 conv. so we can make this (3x3 + 1x1 + residual connection) a single conv3x3 layer

### Structural Reparameterization
- Actually ResNets are hard to prune, worse acc. pruning tradeoff - so this reparametrization will prob become standard in the future for a pruning pipeline
