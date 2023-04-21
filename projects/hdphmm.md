---
layout: custom
permalink: /projects/hdphmm
---


## HDPHMM
Analyzing the driving style and strategies of human drivers could help us understand the differences between racers and develop more competitive trajectories. \uline{ I employed a Bayesian non-parametric approach based on a hidden Markov model (HMM) to identify primitive racing patterns from multi-dimensional time\-series data of time competition around racetracks.}$^2$ I apply a hierarchical Dirichlet process (HDP) to learn the unknown, hidden dynamical modes in the HMM which correspond to  primitive racing patterns as shown in Figure 5.


## Data-driven planning and control
Offline trajectory planning can optimize a full reference trajectory to  minimize lap time while following the dynamics of a model. However,  modeling discrepancies are particularly detrimental when using offline planning, as planning model errors compound with controller modeling errors and can cause the planned trajectory to be infeasible for the real system.  We can compensate for modeling errors by adding an error compensation term to the model equations. In particular, the error can be modeled as a Gaussian Process, the parameters of which are found via Gaussian Process Regression (GPR) by finding the most likely error model that would produce the states observed the system. \uline{We proposed a \textit{double-GPR} error compensation algorithm to reduce model uncertainties}$^3$; specifically we compensate both the offline trajectory planner's model and online controller's model with two respective GPR error compensation functions. We design an iterative framework to re-collect error-rich data using the racing control system. In GTS, our \textit{iterative, double-GPR} compensation functions improve racing performance and iteration stability in comparison to a single compensation function applied merely for real-time control. 



