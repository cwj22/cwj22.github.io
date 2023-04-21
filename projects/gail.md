---
layout: custom
permalink: /projects/gail
---

## Generative Adversarial Imitation Learning
### TLDR;
- End-to-end deep reinforcement learning (RL) can improve an agent's policy through environment interaction.
- Generative adversarial imitation learning (GAIL) builds on RL to learn without access to a reward function by exploiting generative adversarial networks (GANs).
**_Contribution:_** 
I implemented GAIL for autonomous racing by adding the following features to the imitation library
- Importing and processing racing trajectories and calculating new state features
- Adding regulators to the discriminator, including entropy regularization, gradient penalty to enforce Lipshitzness, PU-GAIL
- Implementing Wasserstein GAIL
- Options framework for semi-MDPS
I improve AIL's performance in GTS by exploring 
    - residual policy learning, 
    - exploration with model-based control, 
    - sparse reward guidance.

### Background
Typical RL algorithms (e.g. SAC, PPO) use the following framework:
<div style="text-align: center;">
<figure>
<img src="./figures/rl_diagram.svg" alt="RL Diagram" height="200"/>
    <figcaption>Fig. 1: Typical RL paradigm</figcaption>           
</figure>
</div>

The agent observes a state from the environment, uses it's policy to determine the next action, executes that action in the environment, and observes the next state to repeat the process. The environment gives a reward signal that tells how well the agent is doing, such as the forward course progress made since the last state in racing. The agent's policy is occasionally updated to maximize the expected sum of rewards.

Conversely, generative adversarial Imitation Learning (GAIL) assumes there is no such reward signal, but we have access to demonstrations of an expert interacting in the environment:
<div style="text-align: center;">
<figure>
<img src="./figures/gail_diagram.svg" alt="RL Diagram" height="200"/>
    <figcaption>Fig. 2: Generative Adversarial Imitation Learning</figcaption>           
</figure>
</div>

Rather than a reward signal, GAIL uses generative adversarial networks (GANs) to train a classifier, known as the discriminator, that gives the probability that a given set of states and actions came from the agent or from the expert. The agent's goal is to fool the discrimintor, i.e. maximize the probability that the discrimintor classifies agent's state-actions as coming from the expert. 

### GAIL for autonomous racing in Gran Turismo Sport


### Residual Policy Learning
Residual policy learning ([Silver et al.](https://arxiv.org/abs/1812.06298)) learns a residual NN policy via RL to improve the actions of a base control policy:

<div style="text-align: center;">
<figure>
<img src="./figures/residual_policy.svg" alt="RL Diagram" height="150"/>
    <figcaption>Fig. 3: Residual policy learning</figcaption>           
</figure>
</div>

In vehicle racing, pure-pursuit control is a simple, geometric control algorithm to track a reference path that determines a steering angle based on a lookahead distance on the path. Pure-pursuit control can track paths at low speeds, but is unstable at high speeds and the limits of handling of the vehicle. Residual policy learning can add a NN policy to the output of a pure-pursuit control to improve control performance, while the pure-pursuit control helps guide exploration, speed up training, and outperform NN policies alone. 

We apply GAIL to learn a NN policy on top of a pure-pursuit base controller, speeding up GAIL training and improving performance:

<div style="text-align: center;">
<figure>
<img src="./figures/gail_residual" alt="GAIL Residual Policy Learning Curve" height="150"/>
    <figcaption>Fig. 4: GAIL Residual Policy Learning Curve</figcaption>           
</figure>
</div>


To our knowledge, this is the first time that GAIL has been used for residual policy learning. My preliminary results show that the base control policy reduces required environment interactions, stabilizes learning, and improves control performance.

<div class="row">
  <div class="column">hello</div>
  <div class="column">hello2</div>
</div>

### Options-GAIL for semi-MDPs


### Bootstrapping with GAIL for sparse rewards

