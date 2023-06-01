---
layout: page
title: Open Projects
permalink: /projects/
nav: false
---

<details>
  <summary> Project 1: Multiagent Black-box optimization <span style="color:blue">some *blue* text</span> </summary>
  
Multiagent decision-making arises where a collection of agents collaborate to achieve a common goal. Such problems commonly arise in many smart infrastructure systems such as in collaborative robotics, vehicle fleets, eco industrial parks etc. Here each agent takes its own local decision, but the agent’s actions and decisions may be inter-dependent through common variables or shared constraints.  

Distributed optimization facilitate such a collection of agents to coordinate their actions to global optimality with only limited information sharing. Traditional distributed optimization methods requires detailed models in each subsystem. However, obtaining accurate models may be challenging in many complex engineering systems. Black-box optimization is a purely data-driven alternative that enables us to learn the optimum by interacting with the environment and observing the cost and constraints. Bayesian optimization (BO) is one such data-driven black-box optimization scheme, where the optimum is learned by sequentially interacting with the system. Despite the popularity of Bayesian optimization within AI and computer science domain, a decomposable Bayesian optimization framework for multi-agent systems has not been widely studied.

The main aim of this project is to develop a decomposable Bayesian optimization framework for multi-agent systems. Different decomposition strategies, as well as different Bayesian optimization schemes will be investigated, with application to a vehicle platooning problem and/or integrated energy system.

### Tasks
*	Literature study on distributed optimization and Bayesian optimization
*	Formulate a decomposable Bayesian optimization framework 
*	Investigate different decomposition strategies 
*	Perform simulation studies on a vehicle platooning problem.

### Prerequisites
*	Passionate about optimization and willingness to explore and learn new concepts 
*	Basic understanding of optimization (it would help if you have taken the 4DM20 course).


Please send me an e-mail at d.krishnamoorthy@tue.nl if you want to know more about this topic. 

### Reference:
1. Krishnamoorthy, D. and Paulson, J., 2023. Multi-agent Black-box Optimization using a Bayesian Approach to Alternating Direction Method of Multipliers, IFAC World Congress, Yokohama, Japan.
  
</details>

<details>
  <summary> Project 2: Fast Distributed Model Predictive Control 
 </summary>
  
  Multiagent decision-making occurs when a group of agents collaborates to achieve a shared objective. These scenarios commonly arise in smart infrastructure systems, including collaborative robotics, vehicle fleets, and eco-industrial parks. In such systems, autonomous operation necessitates distributed Model Predictive Control (MPC), where each agent makes decisions locally. However, these actions and decisions may be interconnected through shared variables or constraints.

Due to the interdependencies among subsystems, the MPC subproblems must communicate information to enable coordination. Consequently, whenever new information is received, the MPC problem needs to be solved again. In other words, distributed MPC requires multiple iterations or communication rounds to converge on the optimal solution. This iterative process presents a challenge for real-time control, where timely arrival of the solution is not only desirable but also crucial in many applications. For instance, consider the optimal coordination of autonomous vehicles at traffic intersections [1]. In this case, the coordination of MPCs in each vehicle must reach a solution within a specific timeframe.

While the subproblems solved between consecutive iterations are not identical, they only differ based on the newly received information from other agents. Leveraging this fact, this project will exploit the parametric sensitivities to efficiently compute the subproblem solution using solutions obtained from previous iterations, instead of repeatedly solving the numerical optimization problem at each iteration. Learning-based MPC methods to handle this challenge in distributed MPC will also be studied.

### Tasks
*	Literature study on distributed MPC
*	Formulate a distributed MPC problem and improve its computation time by exploiting its sensitivities
*	Perform a simulation study on a large-scale multi-agent system.

### Prerequisites
*	Passionate about MPC and optimization and willingness to explore and learn new concepts 
*	Basic understanding of optimization and MPC (it would help if you have taken these courses: 4DM20, 5LMB0)

Please send me an e-mail at d.krishnamoorthy@tue.nl if you want to know more about this topic, along with your CV and transcript of records. 

### References
1. Hult, Robert, et al. "Primal decomposition of the optimal coordination of vehicles at traffic intersections." 2016 IEEE 55th Conference on Decision and Control (CDC). IEEE, 2016.
2.  Krishnamoorthy, D. and Kungurtsev, V. (2022),  A Sensitivity Assisted Alternating Directions Method of Multipliers for Distributed Optimization, IEEE Conference on Decision and Control (CDC). 

</details>



