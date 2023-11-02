---
layout: custom
permalink: /control
---

## Data-Driven Methods for Control

### <span style="color:#7030A0;">Dynamic Movement Primitives <a href="https://sites.google.com/berkeley.edu/racingdmp/home">(Project Website)</a></span>

<div class="prof-head" style="margin-left:0px;color:#7030A0;">
Real-time Trajectory Generation via Imitation Learning of Dynamic Movement Primitives for Autonomous Racing
</div>
<blockquote>
We employ sequences of motion primitives for real-time trajectory planning in racecar control with Dynamic Movement Primitives (DMPs).  We introduce the Acceleration goal (Acc. goal) DMP, extending the DMP's target system to accommodate accelerating targets. When sequencing DMPs to model long trajectories, our (Acc. goal DMP explicitly models acceleration at the junctions where one DMP meets its successor in the sequence. Applicable to DMP weights learned by any method, the proposed DMP generates trajectories with less aggressive acceleration and jerk during transitions between DMPs compared to second-order DMPs. Our proposed DMP sequencing method can recover from trajectory deviations, achieve competitive lap times, and maintain stable control in autonomous vehicle racing within the high-fidelity racing game Gran Turismo Sport.
</blockquote>

<div style="display:flex;justify-content:space-between;align-items:center">
<img src="projects/sections.png" height='200' alt="projects"> <iframe width="562" height="337" src="https://www.youtubeeducation.com/embed/8_GEzYPwz4s" title="Real-time Trajectory Generation via Dynamic Movement Primitives for Autonomous Racing" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
</div>


<iframe width="562" height="337" src="https://www.youtubeeducation.com/embed/JLMbpiywVxQ?modestbranding=1&autohide=1&showinfo=0&controls=1&rel=0" title="Real-time Trajectory Generation via Dynamic Movement Primitives for Autonomous Racing" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

<iframe width="560" height="315" src="https://www.youtube.com/embed/8_GEzYPwz4s?modestbranding=1&autohide=1&showinfo=0&controls=1&rel=0" frameborder="0" allowfullscreen></iframe>


#### <span style="color:#7030A0;">Highlight of my Contributions:</span>

- Derived the theoretical framework that extended the discrete options-based semi-MDP framework to encompass <i>skills</i>, which employ a continuous latent space and fixed time horizons
- Extended the skill-based semi-MDP formulation to a framework of two augmented MDPs so that the high-level and low-level policies could be optimized in parallel
- Theoretically justified the use of inter-related Q functions to improve performance of the low-level policy by incorporating the value assigned by high-level skills
- Summarized the results of the research in the paper and actively engaged in a rebuttal to refine and defend the research
<br>

#### <span style="color:#7030A0;">Visit the <span style="font-size:14pt;color:#7030A0;" class="emoji-text">🔗</span> <a href="https://sites.google.com/view/skill-critic">Project Website</a> for the code and manuscript, videos, and more information about this project.</span>

