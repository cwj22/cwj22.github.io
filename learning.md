---
layout: custom
permalink: /learning
---
## End-to-end Learning Projects

<img src="projects/part2.svg" height='200' alt="projects">

### Project 1: Sparse Reward Reinforcement Learning

<div class="prof-head" style="margin-left:0px">
<b>Skill-Critic</b>: Refining Learned Skills for Hierarchical Reinforcement Learning
</div>
<blockquote>
Our Skill-Critic algorithm optimizes both the low and high-level policies of a hierarchial agent, AND these policies are  initialized and regularized by a latent space learned from offline demonstrations to guide the joint policy optimization. We validate our approach in multiple sparse RL environments, including a new sparse reward autonomous racing task in Gran Turismo Sport. The experiments show that Skill-Critic's low-level policy fine-tuning and demonstration-guided regularization are essential for optimal performance.
</blockquote>

<div style="display:flex;justify-content:space-between;align-items:center">
<img src="projects/skillcritic.svg" height='200' alt="projects"> <img src="projects/trajectory_animation.gif" height='350' alt="projects">
</div>

#### Highlight of my Contributions:

- Derived the theoretical framework that extended the discrete options-based semi-MDP framework to encompass <i>skills</i>, which employ a continuous latent space and fixed time horizons
- Extended the skill-based semi-MDP formulation to a framework of two augmented MDPs so that the high-level and low-level policies could be optimized in parallel
- Theoretically justified the use of inter-related Q functions to improve performance of the low-level policy by incorporating the value assigned by high-level skills
- Summarized the results of the research in the paper and actively engaged in a rebuttal to refine and defend the research

Visit the <span style="font-size:14pt;color:" class="emoji-text">🔗</span> <a href="https://sites.google.com/view/skill-critic">Project Website</a> for the code and manuscript, videos, and more information about this project.