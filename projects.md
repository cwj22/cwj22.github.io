---
layout: custom
permalink: /projects
---


My research explores planning and control of complex robotic systems, merging techniques from
engineering and model-based control with advances in computer science and machine learning. My
work particularly emphasizes challenging robotics problems that are difficult even for the average
human operator to perform, such as vehicle racing, where there is often limited access to large expert
datasets and optimal control can be difficult to quantify. I leverage model-based control and machine
learning to advance the capabilities of control algorithms




Autonomous racing has become a popular sub-topic of autonomous driving in recent years and is a complex problem: the vehicle must be controlled at its limit of handling and achieve human-level racing performance. I have worked in collaboration with Sony AI for four years to tackle the challenge of autonomous racing in the  high-fidelity racing simulator Gran Turismo Sport (GTS). However, my planning, control, and machine learning algorithms are not limited to autonomous racing, and in the future I plan to expand into other challenging robotic domains, such as unmanned aerial vehicles, autonomous driving in urban environments, mobile robots, and industrial robotics.


## Model-Based Planning and Control
State-of-the-art model-based planning and control methods can achieve impressive performance by using physical models to inform the planning and control problems. In addition to robotic systems, I helped develop a model of a micro-combined heat and power system (micro-CHP) in Figure 1. The micro-CHP consists of a fuel cell, whose water-based coolant system stores waste heat for household use. By modeling the fuel cell and coolant line, I developed a model that was later used for planning and control.$^1$ In autonomous racing at the limits of handling, nonlinear tire dynamics have a large effect on traction and overall vehicle dynamics, and we thoroughly investigated the effects of different model considerations of a dynamic bicycle model (Figure 2).
 In particular, we explored separate planning and control modules consisting of an offline trajectory planner and an online Model Predictive Control (MPC) tracking controller.$^2$
Our proposed high fidelity model-based control framework can achieve top $0.95\%$ lap time among human-expert players in GTS. 




## Data-driven planning and control
Offline trajectory planning can optimize a full reference trajectory to  minimize lap time while following the dynamics of a model. However,  modeling discrepancies are particularly detrimental when using offline planning, as planning model errors compound with controller modeling errors and can cause the planned trajectory to be infeasible for the real system.  We can compensate for modeling errors by adding an error compensation term to the model equations. In particular, the error can be modeled as a Gaussian Process, the parameters of which are found via Gaussian Process Regression (GPR) by finding the most likely error model that would produce the states observed the system. \uline{We proposed a \textit{double-GPR} error compensation algorithm to reduce model uncertainties}$^3$; specifically we compensate both the offline trajectory planner's model and online controller's model with two respective GPR error compensation functions. We design an iterative framework to re-collect error-rich data using the racing control system. In GTS, our \textit{iterative, double-GPR} compensation functions improve racing performance and iteration stability in comparison to a single compensation function applied merely for real-time control. 


When a controller tracks a fixed (unchanging) reference trajectory, the controller can be unreliable if the state
deviates significantly from the reference trajectory. Trajectory
generation from the observed state can mitigate this instability,
but doing so online can be computationally prohibitive for complex systems. Dynamic Movement Primitives (DMPs) are goal-driven motion
primitives that generate trajectories driven from the
current state to a demonstrated trajectory while imitating the
dynamics of the demonstration. Sequences of DMPs
joined together can describe long trajectories; however,
existing methods to sequence DMPs with acceleration dynamics
require many demonstrations or suffer from increased compu-
tation as the number of sequences increases. We implement a
sequence of DMPs imitation learning method that generates
trajectories from consecutive DMPs using the time duration of
each motion primitive. My novel \textit{Acc. goal} DMP 
models non-zero acceleration at junctions of DMP sequences,
lowering acceleration and jerk in trajectories generated
from sequences of DMPs compared to existing methods. \uline{My
framework generates online racing trajectories for an MPC for
a racecar in GTS, better
recovering from deviations than standard MPC.}$^4$ Furthermore,
the novel DMP formulation generates trajectories with less
online tracking error, less aggressive control commands, and
faster lap times than other DMP formulations.





## Data-driven driver analysis and end-to-end learning

Analyzing the driving style and strategies of human drivers could help us understand the differences between racers and develop more competitive trajectories. \uline{ I employed a Bayesian non-parametric approach based on a hidden Markov model (HMM) to identify primitive racing patterns from multi-dimensional time\-series data of time competition around racetracks.}$^2$ I apply a hierarchical Dirichlet process (HDP) to learn the unknown, hidden dynamical modes in the HMM which correspond to  primitive racing patterns as shown in Figure 5.

In my current work, I am exploring generative adversarial imitation learning (GAIL) for autonomous racing, which leverages generative adversarial networks and reinforcement learning to learn a neural network policy that imitates expert demonstrations by sending an action based on the current observed state. A  binary classifier, known as the discriminator, is trained to distinguish between expert trajectories and trajectories sampled by the current policy. In particular, I am applying the Option-GAIL framework$^6$ to the autonomous racing problem by applying hierarchical reinforcement learning to find a high-level option-picking policy and a low-level action-picking policy. Rather than inferring the expert's options using the current policy, I employ HDP-HMM to identify the expert's options from the expert's trajectory. \uline{By leveraging HDP-HMM, the expert's options can be learned prior to training the high and low-level policies, stabilizing training and outperforming policy-inferred options.}


