## Compacting, Picking and Growing

| Title | Authors | In One Sentence | Summary | Date | Link | Conference |
| -----  | ------ | --------------- | ------- | ---- | ---- | ---------- |
| Compacting, Picking and Growing for Unforgetting Continual Learning | Steven C.Y. Hung et al. | Leveraging Pruning and Progressive Networks Expansion can deal with catastrophic forgetting while retaining model compactness. | [Summary](./paper-summary/continual-learning/CompactingPickingGrowing.md) | 18/06/2019 | [Paper](https://proceedings.neurips.cc/paper/2019/file/3b220b436e5f3d917a1e649a0dc0281c-Paper.pdf) | NeurIPS 2019 | 


### Abstract
- Integrating pruning and progressive network expansion allows for dealing with catastrophic forgetting while scaling up to sequential tasks - while maintaining model compactness.

### Introduction
- Pretraining and fine-tuning a new FC layer leads to catastrophic forgetting
- A common solution to this problem is regularization of weights or gradients (f.e. search for common convergence for current and previous task)
- Another example: Elastic-Weight-Consolidation (EWC) uses distillation for regularization by imposing constraints on neural weights adapted from teacher to student network. 
- These solution strategies do not work wel for an infinite number of sequential tasks in which earlier training data is missing. 
- To address data-missing issues : data-preserving and memory-replay techniques have been used: f.e. save important data samples or use GANs for keeping data information -> Problem: requires explicit retraining using old information
- Limited architecture cannot be ensured to remember the skills incrementally learned from unlimited tasks -> Add some progressive element
- This continuous retraining of a knowledge base allows for reusable skills across tasks
- So lets tackle these issues: reuse old weights directly to avoid catastrophic forgetting, enlarge the network by adding nodes for new tasks (cf. ProgressiveNet)
- We dont want such a complicated structure like ProgressiveNet that keeps growing, so that is why we compress in-between stages -> We can choose to recycle or retrain the weights we just killed for the new task.
- Another distinction: **Picking Step**: Do not employ all old-task weights but pick only some critical ones via a differentiable mask. (so not only pruning but also another discarding step if I understand it correctly)
- To assess pruning ratio, prune and retrain with accuracy retention goal.

### Related Work
- **Network Regularization**: Restrictively update model weights
- **Memory Replay**: Use GAN to remember data information
- **Dynamic Architecture**: Add weights/layers

### Method
- Task 1: Train and prune. After pruning (not really pruning but identified as not needed weights): we have a group of useful nodes for the task and non-useful ones.
- Task k to k+1: We have k sets of Weights that we need for earlier tasks. - We also have our group of non-useful weights for earlier tasks that can be employed for tasks to come. For the new task we train a mask to use part of the earlier weights as well as we allow it to use the released weights. If accuracy is not satisfactory we add weights
