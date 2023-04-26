---
layout: custom
permalink: /projects/dmp
---


## Dynamic movement primitives for fast online racing trajectories
### TLDR;
- Dynamic movement primitives (DMPs) are useful motion primitives that are composed of a target-driven system and an arbritrary nonlinear system modeled by weighted Guassian kernels.
- I propose an _Acceleration goal_ DMP that extends the a DMP's target system
to handle accelerating targets.
- Our _Acc. goal_ DMP generates trajectories with less
aggressive acceleration and jerk when transitioning
between DMPs in sequence than second order DMPs.
- We generate online DMP trajectories for control in
GranTurismo Sport.
- Our method recovers from starting states where a base-
line controller fails and yields less tracking error, less
aggressive control, and the lowest lap-time compared
to existing methods.
### Trajectory Generation from a Sequence of DMPs
#### Background
_Motivation:_ Online trajectory planning improves a system's adaptability and performance in complex and dynamic environments. Motion primitives are a computationally efficient solution to trajectory generation challenges by using pre-defined basic motion patterns.

Dynamic Movement Primitives (DMPs) model movements as non-linear differential equations. The original second order DMP was proposed by [Kober et al.](https://ieeexplore.ieee.org/document/5509672/):

<div style="text-align: center;">
<figure>
<img src="./eqns/dmp/dmp2.svg" alt="2nd order DMP equations" height="200"/>       
</figure>
</div>

The DMP is composed of two systems: the <font color="#1212FF">goal-attracted system </font>is driven toward the target state and the <font color="#7030A0">transformation function </font> describes the arbitrary dynamics of the trajectory. The arbitrary motion of the transormation function is determined by a weighted sum of Gaussian kernels:
<div style="text-align: center;">
<figure>
<img src="./eqns/dmp/transformation.svg" alt="2nd Order DMP equations" height="140"/>       
</figure>
</div>


For more information on DMPs, see the review by [Saveriano et al.](https://arxiv.org/pdf/2102.03861.pdf).


#### Proposed _acceleration goal_ DMP
Racing trajectories require accurate dynamics for optimal performance. Therefore I raise the order of the DMP:
<div style="text-align: center;">
<figure>
<img src="./eqns/dmp/dmp3.svg" alt="3rd Order DMP equations" height="180"/>       
</figure>
</div>
Here I propose two changes to the original DMP: 
1. Raise the order of the DMP dynamic equation to the third order
2. Adapt the moving target system to include acceleration to allow non-zero acceleration at target states.

#### Trajectory generation algorithm
Armed with the _acceleration goal_ DMP, I can now accurately model a racing trajectory as a sequence of motion primitives (DMPs):
<div style="text-align: center;">
<figure>
<img src="./figures/annotatedsections.svg" alt="DMP sections" height="280" 
/>
</figure>
</div>
Each DMP section is described by a set of weights, $\Theta_j$, and the final or goal state, $G_j$. This allows me to generate new trajectories, $P_G$, of duration $T_G$ using Algorithm 1.
<div style="text-align: center;">
<figure>
<img src="./figures/algorithm.svg" alt="DMP Trajectory Generation Algorithm" height="320" 
/>
</figure>
</div>
 Specifically, we find the index, $m$, of the closest demonstration waypoint to the observed position; this waypoint corresponds to the $j$-th segment and a reference time in the segment $t_m\in[0,T_S)$. The DMP equations give the derivative of generated trajectory at the desired time steps, starting from reference time $t_m$ (Line 8). If the generated trajectory is integrated to the end (in time) of the current segment (Line 10), it will switch to the DMP information of the following segment ($G_{j+1}, \Theta_{j+1}$), and the reference time is reset to start at the beginning of the subsequent segment (Line 13}).

We employ a model predictive controller (similar to [my other project](https://cwj22.github.io/projects/mpc.html)) to generate the steering and throttle command to track the generated reference trajectories. 

### Control Experiments in Gran Turismo Sport
#### Comparison of DMP methods at different track locations

#### Comparison of tracking error and control commands

#### Lap time comparison