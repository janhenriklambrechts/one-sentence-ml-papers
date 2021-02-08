| Title | Authors | In One Sentence | Summary | Date | Link | Conference |
| -----  | ------ | --------------- | ------- | ---- | ---- | ---------- |
| AutoSlim: Towards One-Shot Architecture Search for Channel Numbers  | Train a single slimmable network and then greedily slim the layer with least accuracy drop for one-shot NAS | [Summary](./paper-summary/nas/autoslim.md) | 01/06/2019 | [Paper](https://arxiv.org/pdf/1903.11728.pdf)| ArXiv | 

### Abstract
- Train a single slimmable network and then iteratively evaluate channel configurations instead of complicated DRL

### Introduction
- We could bruteforce channel search for different layers but training slimmable models is much faster
- Train for a few epochs and then slim the layers that can have it
- After slimmable training, the weight is implicitly ranked by its index -> Instead of finding out which ones are the most important- Works really well!
