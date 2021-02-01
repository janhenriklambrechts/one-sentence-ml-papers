| Title | Authors | In One Sentence | Summary | Date | Link | Conference |
| -----  | ------ | --------------- | ------- | ---- | ---- | ---------- |
| Continual Learning with Hypernetworks | Johannes von Oswald et al. | To overcome gigantic network growth for new tasks, we build a network generator that has less weights | [Summary](./paper-summary/continual-learning/CLwithHN.md) | 12/02/2020 | [Paper](https://arxiv.org/pdf/1906.00695.pdf)| ICLR 2020 | 

### Abstract
- Instead of recalling input-output relations of previously seen data, task-conditioned hypernetworks only require rehearsing task-specific weight relaizations.
- Extremely long memory lifetimes are achieved using this approach

### Introduction
- We make a task embedding and feed this to a weight generator that generates the final weightmaps for all the tasks. Task embeddings need to be remembered
- How is this better? Instead of needing to fix outputs for all samples belonging to a specific task, we just need to retain 1 input - output pair (task vector + weightsoutput)
- You do not only need full embedding but also chunk embeddings to generate the weights in chunks 


### Context-free inference (unknown task identity)
- Use entropy of output predictions to choose task identity - quite naive but very easy to implement -> Novelty detection
- using a GAN is often in the real world the SOTA solution

### Experiments

- Model does well in all settings: 1) Given Task Identity 2) No Task Identity

