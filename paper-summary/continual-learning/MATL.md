## Mutual Alignment Transfer Learning

| Title | Authors | In One Sentence | Summary | Date | Link | Conference |
| -----  | ------ | --------------- | ------- | ---- | ---- | ---------- |
| Mutual Alignment Transfer Learning | Markus Wulfmeister et al. | Demonstrates that auxilary rewards can bridge the gap between simulation and real-world robots | [Summary](./paper-summary/continual-learning/MATL.md) | 26/09/2017 | [Paper](https://arxiv.org/pdf/1707.07907.pdf)| CoRL 2017 | 

### Abstract
- RL does really well in games and simulations but fails at robot application level
- Although sample complexity for robots can reduced by training policies in simulations, such policies can perform sub-optimally on the real platform given imperfect calibration of model dynamics
- Idea: give auxiliary rewards in stimulation for states in which model in real world is often in to help exploration

### Introduction
- Winning at Chess and Go harnesses virtually unlimited available training data because parallelizable and significantly faster than real life
- Real life: slow and expensive task executions, difficult to give direct feedback as well -> GAP
- This is why we like emulators. but they are not exact replications of real life platforms and environments -> So we use fine-tuning. -> Problem: policies are often overfitting on simulation (exploiting rather than mastering it).
- Idea: mutually explore the others statespace: Let Real Robot visit more states that Sim Robot is in (because sim robot knows these well) and let Sim Robot explore states that Real Robot is often in (so it can learn these states well). 
### Experiments
- Works well, but tuning is annoying 
