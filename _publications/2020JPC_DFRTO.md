---
title: "A Distributed Feedback-based Online Process Optimization Framework for Optimal Resource Sharing  
"
collection: publications
permalink: '/publication/2020JPC_DFRTO'
excerpt: ''
date: 2020-11-22
venue: 'Journal of Process Control'
---


[Download paper here](http://folk.ntnu.no/dineshk/Papers/DFRTO.pdf)

[Published version](): To Appear

### Authors
 Dinesh Krishnamoorthy

### Abstract 
Distributed real-time optimization (RTO) enables optimal operation of large-scale process systems with common resources shared across several clusters. 
Typically in distributed RTO, the different subsystems are optimized locally, and a centralized master problem is used to coordinate the different subsystems in order to reach system-wide optimal operation. This is especially beneficial in industrial symbiosis, where only  limited information can be shared between the different clusters.
However, one of the main challenges with this approach is the need to solve  numerical optimization problems online for each subsystem. With the recent surge of interest in feedback optimizing control, where the optimization problem is converted into a feedback control problem, this paper proposes a distributed feedback-based RTO (DFRTO) framework for optimal resource sharing in an industrial symbiotic setting. In this approach, a master coordinator updates the shadow price for the shared resource, and the different subsystems locally optimize their operation using feedback control for the given shadow price. The proposed framework is shown to converge to a stationary point of the system-wide optimization problem, and is demonstrated using an industrial symbiotic offshore oil and gas production system with shared resources. 
