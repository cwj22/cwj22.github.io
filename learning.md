---
layout: custom
permalink: /learning
---
## End-to-end Learning Projects

<img src="projects/part2.svg" height='200' alt="projects">

### <span style="color:#7030A0;">Sparse Reward Reinforcement Learning  <a href="https://sites.google.com/view/skill-critic">(Project Website)</a></span>

<div class="prof-head" style="margin-left:0px;color:#7030A0;">
<b>Skill-Critic</b>: Refining Learned Skills for Hierarchical Reinforcement Learning
</div>
<blockquote>
Our Skill-Critic algorithm optimizes both the low and high-level policies of a hierarchial agent, AND these policies are  initialized and regularized by a latent space learned from offline demonstrations to guide the joint policy optimization. We validate our approach in multiple sparse RL environments, including a new sparse reward autonomous racing task in Gran Turismo Sport. The experiments show that Skill-Critic's low-level policy fine-tuning and demonstration-guided regularization are essential for optimal performance.
</blockquote>

<div style="display:flex;justify-content:space-between;align-items:center">
<img src="projects/skillcritic.svg" height='200' alt="projects"> <img src="projects/trajectory_animation.gif" height='350' alt="projects">
</div>

#### <span style="color:#7030A0;">Highlight of my Contributions:</span>

- Derived the theoretical framework that extended the discrete options-based semi-MDP framework to encompass <i>skills</i>, which employ a continuous latent space and fixed time horizons
- Extended the skill-based semi-MDP formulation to a framework of two augmented MDPs so that the high-level and low-level policies could be optimized in parallel
- Theoretically justified the use of inter-related Q functions to improve performance of the low-level policy by incorporating the value assigned by high-level skills
- Summarized the results of the research in the paper and actively engaged in a rebuttal to refine and defend the research

Visit the <span style="font-size:14pt;color:#7030A0;" class="emoji-text">🔗</span> <a href="https://sites.google.com/view/skill-critic">Project Website</a> for the code and manuscript, videos, and more information about this project.



### <span style="color:#ec008c;">Imitation Learning from Human Demonstrations</span>

<div class="prof-head" style="margin-left:0px;color:#ec008c;">
<b>BeT-AIL</b>:  Behavior Transformer-Assisted Adversarial Imitation Learning from Human  Gameplay
</div>
<blockquote>
Our Behavior Transformer-Assisted Adversarial Imitation Learning (BeT-AIL) method leverages BeT sequence modeling and online AIL fine-tuning to learn human-like motion from demonstrations.
We first verify that AIL can train a high performing (i.e. low lap time) policy in GT Sport, even when those demonstrations are collected at different control frequency and the agent's action is delayed due to real-time computation. However, AIL alone does not capture the non-Markovian decision making strategy of humans, and the AIL policy exhibits shaky behavior when analyzing the change in action commands. Therefore, we model real human players as using sequential decision-making with the Behavior Transformer (BeT) and restrict an AIL residual policy to make only minor adjustments to the BeT policy. The contributions are:
<ul>
    <li>We propose a residual AIL policy to fine-tune the BeT policy; the BeT policy models multi-step decision making, and the residual policy adjusts for state distribution shift and differences in the demonstrated trajectories and the agent's environment</li>
    <li>We show a small residual policy allows BeT-AIL to closely match non-Markovian patterns in human demonstrations while still significantly improving online performance</li>
    <li>We learn an autonomous racing policy solely from trajectories from real human gameplay in Gran Turismo (GT) Sport.</li>
</ul>
</blockquote>

<div style="display:flex;justify-content:space-between;align-items:center">
<img src="projects/transformerassisted.svg" height='200' alt="projects"> <img src="projects/finishedlaps.svg" height='350' alt="projects">
</div>

#### <span style="color:#ec008c;">Highlight of my Contributions:</span>

- Full development of the BeT-AIL algorithm, including decision to use the Behavior Transformer, residual policy, and adversarial imitation learning
- Adaptation of existing code-bases to include residual policy, multiple different types of regularization on the discriminator network, and extended features in PPO and SAC algorithms 
- Code implementation of gym environment and calculation of track-related state features for both demonstrations and environment
- Experiment design and execution, including design of configuration files to handle all baseline and hyperparameter choices
- Currently finalizing paper manuscript for submission

Please stay tuned for a project website and paper manuscript. Initial draft available by request under select circumstances.


