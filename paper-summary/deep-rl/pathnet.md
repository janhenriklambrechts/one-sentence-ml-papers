## PathNet
| PathNet: Evolution Channels Gradient Descent in Super Neural Networks | Genetic Algorithm that replicates and mutates earlier paths for faster transfer learning | [Summary](./paper-summary/deep-rl/pathnet.md) | 19/11/2019 | [Paper](https://arxiv.org/pdf/1701.08734.pdf)| ArXiv | 

### Abstract 
- For efficient AGI we want parameter sharing across tasks, without catastrophic forgetting
- PathNet finds detects reusable paths in a tournament genetic algorithm that assesses fitness according to a cost function, employing and mutating these useful paths 
- Fix paths on Path A and re-use parts of the optimal path for B

### Introduction
- Most efficient way for NN to gain experience is to reuse knowledge from earlier tasks
- Idea: **Learn an agent that copies or reuses paths from the previous network**
- Evolution algorithm guides **where gradient descent should be applied**
- Compared to ProgressiveNet, we do not hardwire the architecture
- **Reinitialization is key to do better than finetuning**
### Experiments
- Works across Atari and MNIST/CIFAR






