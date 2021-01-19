## MuZero

| Title | Authors | In One Sentence | Summary | Date | Link | Conference |
| -----  | ------ | --------------- | ------- | ---- | ---- | ---------- |
| Mastering Atari, Go, Chess and Shogi by Planning with a Learned Model  | Tree search and learned model can master unknown and complex environments | [Summary](./paper-summary/deep-rl/muzero.md) | 19/11/2019 | [Paper](https://arxiv.org/abs/1911.08265)| ArXiv | 

### Abstract
- Tree-based methods have done very well in Chess and Go, where a perfect simulator is available, yet irl the dynamics governing the environment are often complex and unknown.
- MuZero matches AlphaZero without knowledge of game rules of Go, chess and shogi

### Introduction
- Planning algorithms (lookahead search) has allowed machines to win in chess, Go, poker and ... 
- Yet these algos require knowledge of environments dynamics (f.e. rules of the game or an accurate simulator). This makes them unviable for real worlds domains like robotics, industrial control or intelligent assistants
- Before: **Model-based RL**: learn a model of the environments dynamics and then plan with respect to the learned model. -> Better: **Model-free RL**: estimate optimal policy and/or value function directly from interactions with the environment -> Better: **planning algos** (but then we require a model)
- MuZero builds upons AlphaZero search and search-based algorithm: (1) Learns a model at the same time; (2) includes single agent domains and non-zero rewards at intermediate steps- **Main idea: predict those aspects of the future that are directly relevant for planning**
- Model receives input (f.e. image of the Go board) and transforms it into a hidden state.  
- **Hidden state**: updated iteratively by a recurrent process that receives the previous hidden state and a hypothetical next action. 
- **Every step**: model predicts **policy** (move to play), **value function** (predicted winner) and **immediate reward** (points scored by playing move). --> Only optimize for these values, not trying to emulate a model, just learn what is useful for learning a good policy.

### Prior Work
**Reinforcement Learning**
- **Model-based**: MDP: consists of two components **state transition model** (predicts next state) and **reward model** (predicts future reward) -- after model has been built it can be optimized with value-iteration or Monte-Carlo Tree Search
-> Common approach: **directly modeling the observation stream at pixel-level** (not computationally feasible for scale) --> Move to latent space and make it feasible to reconstruct at pixel-level with this latent space. ==> All these options lag behind well-tuned model-free methods
- **Model-free**: end-to-end predicting the value function (idea is to construct an abstract MDP that matches the real-world environment) -- The MDP is viewed as a hidden layer of a deep neural network

### MuZero Algorithm 
- At each timestep t the model is represented by 
1. **Representation function**: s_i = h_theta(o_1, ..., o_t)
2. **Dynamics function**: r_k, s_k = g_theta(s_(k-1), a_k) --> mirrors an MDP (in comparison to previous work this s_i does not have environment semantics attached to it)
3. **Prediction function**: p_k, v_k = f_theta(s_k)











