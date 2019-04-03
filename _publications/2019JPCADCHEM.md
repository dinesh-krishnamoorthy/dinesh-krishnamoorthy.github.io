---
title: "A Primal decomposition algorithm for distributed multistage scenario model predictive control"
collection: publications
excerpt: ''
permalink: '/publications/2019JPCADCHEM'
date: 2019-02-08
venue: 'Journal of Process Control (ADCHEM Special issue invited paper)'
---

[Download paper here](http://folk.ntnu.no/dineshk/Papers/2019/JPC_Scenario%20Decomposition.pdf)

Abstract: 

This paper proposes a primal decomposition algorithm for efficient computation
of multistage scenario model predictive control, where the future evolution of
uncertainty is represented by a scenario tree. This often results in large-scale
optimization problems. Since the different scenarios are only coupled via the socalled non-anticipativity constraints, which ensures that the first control input
is the same for all the scenarios, the different scenarios can be decomposed
into smaller subproblems and solved iteratively using a master problem to coordinate the subproblems. We review the most common scenario decomposition
methods and argue in favour of primal decomposition algorithms, since it ensures
feasibility of the non-anticipativity constraints throughout the iterations which
is crucial for closed-loop implementation. We also propose a novel backtracking
algorithm to determine a suitable step length in the master problem to ensure
the feasibility of the nonlinear constraints. The performance of the proposed
approach and the backtracking algorithm is demonstrated using a CSTR case
study



Recommended citation: (In-Press).
