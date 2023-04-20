---
layout: custom
permalink: /projects/gail
---

## Adversarial Imitation Learning
### TLDR;
- End-to-end deep reinforcement learning (RL) can improve an agent's policy through environment interaction.
- Adversarial imitation learning (AIL) builds on RL to learn without access to a reward function by exploiting GANs.
- _Contribution:_ I improve AIL's performance in GTS by exploring residual policy learning, exploration with model-based control, options framework for semi-MDPS, and sparse reward guidance.


Typical RL algorithms (e.g. SAC, PPO) use the following framework:
![RL Diagram](./figures/rl_diagram.svg)
<img src="rl_diagram.svg" alt="RL Diagram" width="20"/>

![GAIL Diagram](./figures/gail_diagram.svg)

<object data="/figures/annotatedplot.pdf" width="1000" height="1000" type='application/pdf'></object>

