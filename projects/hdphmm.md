---
layout: custom
permalink: /projects/hdphmm
---




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
