## NetTailor: Tuning the architecture, not just the weights

| Title | Authors | In One Sentence | Summary | Date | Link | Conference |
| -----  | ------ | --------------- | ------- | ---- | ---- | ---------- |
| NetTailor: Tuning the Architecture, Not just the Weights | Pedro Morgado et al. | Tuning the architecture, not just the weights | [Summary](./paper-summary/continual-learning/NetTailor.md) | 29/06/2019 | [Paper](http://www.svcl.ucsd.edu/~morgado/nettailor/nettailor.pdf)| CVPR 2019 | 


### Abstract
- Real-world applications of OD often want multiple tasks on a single platform
- Normally: reuse the complete CNN, and fine-tune it on target task. 
- This work: use some pretrained blocks and regularity constraint to end up with a smaller network -- this allows it to grow smaller than original network after finetuning procedure.
