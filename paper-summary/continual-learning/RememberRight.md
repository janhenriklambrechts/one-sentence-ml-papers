| Title | Authors | In One Sentence | Summary | Date | Link | Conference |
| -----  | ------ | --------------- | ------- | ---- | ---- | ---------- |
| Remembering for the Right Reasons: Explanations Reduce Catastrophic Forgetting | Sayna Ebrahimi et al. | Use saliency maps for experience replay to reduce catastrophic forgetting even more | [Summary](./paper-summary/continual-learning/RememberRight.md) | 25/01/2021 | [Paper](https://openreview.net/pdf?id=tHgJoMfy6nI)| ICLR 2021 | 

### Abstract
- Replay buffers help, but they dont give the model more explanation to reduce performance on prior tasks - what if we give it the evidence
- Adding saliency maps shows why a model made a certain prediction

### Introduction
- Small memory budgets has led people to store data points, gradients, online generative models, feature maps or attention maps etc.
- Any saliency model works, smoothgrad, vanill backprop, gradcam etc.
- Do a L1 loss between new grad and older one

### Few-Shot Class Incremental Learning
- Setting where we start with trained model on b base calsses and then get C new classes with K little samples. Adding saliency maps improves earlier methods in this few-shot setting as well.

### Personal comment
- Not terribly exciting given the fact that of course adding extra "labels" in a setting in which we dont have a lot of labels will improve catastrophic forgetting
- Interesting in the sense that it seems useful to look into better methods (less storage space) that we can learn from 
