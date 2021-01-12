## Progressive Neural Networks

| Title | Authors | In One Sentence | Summary | Date | Link | Conference |
| -----  | ------ | --------------- | ------- | ---- | ---- | ---------- |
| Progressive Neural Networks | Andrei A. Rusu, Neil C. Rabinowitz et al. | Grow lateral connections to features learned by frozen weights | [Summary](./paper-summary/continual-learning/ProgressiveNetworks.md) | 01/01/2016 | [Paper](https://arxiv.org/pdf/1606.04671.pdf) | Arxiv | 

### Abstract
- Learning to solve complex sequences of tasks -> Leveraging earlier knowledge // X Catastrophic forgetting remains a key obstacle
- Progressive Networks are a step forward: leverage prior knowledge via lateral connections to previously learned features

### Introduction
- Transfer Learning normally: Finetuning remains a method of choice for transfer learning with neural networks.
    -> This approach does not work well for multi-task learning
        -> Catastrophic forgetting
        -> Distillation helps but requires us to keep previous data which we do not want

### Progressive Networks
- Catastrophic forgetting is prevented by freezing columns, transfer learning is allowed by lateral connections
- Problems: 1) Requires predefined task knowledge 2) Explosive growth of parameters
    -> Left for future work
