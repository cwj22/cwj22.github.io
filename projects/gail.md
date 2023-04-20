---
layout: custom
permalink: /projects/gail
---



## Adversarial Imitation Learning
### TLDR;


### Background
Distribution shift 
Adversarial imitation learning (AIL) is a method that can combine the strengths of deep reinforcement learning and imitation learning. AIL leverages generative adversarial networks (GANs) and reinforcement learning (RL) to learn a neural network (NN) policy that imitates expert demonstrations by sending an action based on the current observed state. A  binary classifier, known as the discriminator, is trained to distinguish between expert trajectories and trajectories sampled by the current policy. The goal of the discriminator is to determine whether state-action tuples (s,a) came from an expert demonstration or from the policy, and the goal of the policy is to ``trick'' the discriminator into thinking it's actions are the same as the expert demonstrator's actions. 

![Sections](./figures/sections.svg)

<object data="/figures/annotatedplot.pdf" width="1000" height="1000" type='application/pdf'></object>

