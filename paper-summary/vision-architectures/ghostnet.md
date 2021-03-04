| Title | Authors | In One Sentence | Summary | Date | Link | Conference |
| -----  | ------ | --------------- | ------- | ---- | ---- | ---------- |
| GhostNet: More Features from Cheap Operations | Kai Han et al. | Transforming little feature maps with simple linear operations to many feature maps works very well | [Summary](./paper-summary/vision-architectures/ghostnet.md) | 13/03/2020 | [Paper](https://arxiv.org/pdf/1911.11907.pdf)| ArXiv | 

### Abstract
- Succesful CNNs often have a large redundacy in feature maps
- Ghost Module: create limited amount of normal feature maps and concatenate linear transformations of these original feature maps

### Introduction
- Some feature maps look redundant - like a ghost of another feature map. As such the authors embrace this redundancy and aim to achieve this redundancy with cheaper operations
- Difference: instead of depthwise conv they use a linear transformation that can have 3x3 kernel or 5x5
- Actually the GhostNet method works incredibly well on ImageNet
- Works reasonably well on OD as well
