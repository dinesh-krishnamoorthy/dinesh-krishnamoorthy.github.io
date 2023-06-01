---
layout: page
title: Open Projects
permalink: /projects/
nav: false
---

<details>
  <summary> Project 1: Multiagent Black-box optimization </summary>
  
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

<details>
  <summary> Project 3: Mixed integer Model Predictive Control using Value Function Approximation
 </summary>
 
 Application of nonlinear model predictive control (NMPC) to problems with hybrid dynamical systems, disjoint constraints, or discrete controls often results in mixed-integer formulations with both continuous and discrete decision variables. However, solving the resulting mixed-integer nonlinear programming problems (MINLP) in real-time is challenging. This can be a serious limiting factor in many applications. 

To address the computational complexity of solving mixed integer nonlinear model predictive control problem in real-time, the aim of this master project is to explore the idea of approximating mixed integer NMPC formulations using value function approximation. Leveraging Bellman's principle of optimality, the key idea here is to divide the prediction horizon into two parts, where the optimal value function of the latter part of the prediction horizon is approximated offline using expert demonstrations. Doing so allows us to solve the Mixed integer NMPC problem with a considerably shorter prediction horizon online, thereby reducing the online computation cost. 

The goal of this master thesis is to develop a mixed integer NMPC formulation based on value function approximation and apply it to an engineering case study such as process control, automotive system, or nuclear fusion.

### Tasks
* Literature study on mixed integer MPC and learning-based MPC
*	Formulate a mixed integer MPC problem with a cost-to-go approximation 
*	Investigate different approaches to learn the cost-to-go function (e.g. inverse optimization, supervised learning)
*	Perform a simulation study on a suitable application example

### Prerequisites
*	Passionate about optimization and willingness to explore and learn new concepts 
*	Basic understanding of optimization and MPC (it would help if you have taken these courses: 4SC000, 4DM20, 5LMB0)
 
 Please send me an e-mail at d.krishnamoorthy@tue.nl if you want to know more about this topic, along with your CV and transcript of records. 
 
### References
 
1. Orrico, C. A., van Berkel, M., Bosman, T., Heemels, W.P.M.H., Krishnamoorthy, D., 2023. Mixed-Integer MPC Strategies for Fueling and Density Control in Fusion Tokamaks, IEEE Control System Letters (In-Press) 


</details>


<details>
  <summary> Project 4:Learning-based Model Predictive Control 
 </summary>
 Model predictive control (MPC) is a popular control strategy for constrained multivariable systems that is based on repeatedly solving a receding horizon optimal control problem at each time of the controller. As the range of MPC application extends beyond the traditional process industries, additional challenges such as computational effort and memory footprint need to be addressed. One approach to eliminate the need for solving optimization problems online, is to pre-compute the MPC policy as a function of the states. This can be done by using machine learning techniques. 

Learning-based MPC may either involve learning the underlying model, the cost function, or directly the policy using machine learning techniques. As such, learning-based MPC requires labelled training data sets sampled from the MPC policy. This is typically obtained by sampling the feasible state-space and evaluating the control law by solving the numerical optimization problem offline for each sample. Although the resulting approximate policy can be cheaply evaluated online, generating large training samples to learn the MPC policy can be time consuming and prohibitively expensive. This is one of the fundamental bottlenecks that limit the design and implementation of learning-based MPC. This project will use a recently proposed data augmentation scheme [1] to efficiently develop learning-based MPC controller offline. Furthermore, online learning techniques for safety critical systems such as robotics and autonomous vehicles will also be developed to improve the controller performance. 

### Tasks
*	Literature study on Learning-based MPC 
*	Formulate a MPC problem for quadcopter control 
*	Setup a framework for learning the MPC policy and perform simulation studies

### Prerequisites
*	Passionate about applications of MPC and optimization, and willingness to explore and learn new concepts 
*	Basic understanding of optimization, MPC, and dynamic programming (it would help if you have taken these courses: 4SC000, 4DM20, 5LMB0)
 
 Please send me an e-mail at d.krishnamoorthy@tue.nl if you want to know more about this topic, along with your CV and transcript of records. 
 
### References
 
1. Krishnamoorthy, D. 2021. A Sensitivity-based Data Augmentation Framework for Model Predictive Control Policy Approximation. IEEE Transactions on Automatic Control. DOI: 10.1109/TAC.2021.3124983
2. Krishnamoorthy, D., 2023. An Improved Data Augmentation Scheme for Model Predictive Control Policy Approximation, IEEE Control System Letters


</details>



