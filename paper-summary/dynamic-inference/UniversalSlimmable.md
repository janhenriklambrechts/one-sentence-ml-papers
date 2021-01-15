## Universally Slimmable Networks

| Title | Authors | In One Sentence | Summary | Date | Link | Conference |
| -----  | ------ | --------------- | ------- | ---- | ---- | ---------- |
| Universally Slimmable Networks and Improved Training Techniques | Jiahui Yu et al. | Makes Slimmable networks able to run at arbitrary widths | [Summary](./paper-summary/dynamic-inference/UniversalSlimmable.md) | [Paper](ihttps://arxiv.org/abs/1903.05134) | ICCV 2019 |

### Abstract 
- Extends Slimmable Networks to run at any width and trains them with Knowledge Distillation

### Introduction
- Slimmable Models are great, but can we run them at arbitrary width?
- We should be able to, namely a slimmable network will always be bounded in their error by width above and below
- How to deal with BN? - After training we freeze the weights and find proper BN value for any width

### Improved Training Techniques
- ground truth label + predicted prob with CE is worse than just using predicted prob with CE
- superresolution: use l_1 or l_2 as training objective at predicted patches
- Deep Reinforcement Learning: use PPO and run policy predicted by model at largest width as roll-out for training other widths.
