| Title | Authors | In One Sentence | Summary | Date | Link | Conference |
| -----  | ------ | --------------- | ------- | ---- | ---- | ---------- |
| Three scenarios for continual learning | Gido van de Ven et al. | Establishes and classifies earlier continual learning scenarios | [Summary](./paper-summary/continual-learning/three-scenarios.md) | 15/04/2019 | [Paper](https://arxiv.org/pdf/1904.07734.pdf)| Arxiv | 

### Abstract
- The field of continual learning suffers from different evaluation protocols across methods, therefore it is difficult to compare performance across them 
- different scenarios are based on whether task identity is provided or not

### Introduction
- Catastrophic forgetting is a real problem
- Continual learning does agree on: 1) only current task data is available, 2) tasks are assumed to be clearly seperated
- Difference occurs in whether task identity is provided or not:
1. **Task-IL**: Solve tasks so far, task-ID provided
2. **Domain-IL**: Solve tasks so far, task-ID not provided
3. **Class-IL**: Solve tasks so far and infer task-ID

- 2) is an agent that needs to survive in different environments but does not necessarily cares what environment it is in (task always the same but input distribution is shifting)
- 3) includes learning new classes incrementally
- Only methods using replay do well on 2) and 3)
