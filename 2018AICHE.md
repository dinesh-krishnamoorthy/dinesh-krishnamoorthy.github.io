---
title: "An Overview and Evaluation of Approaches for Online Process Optimization"
collection: talks
type: "Talk"
permalink: /talks/2012-03-01-talk-1
venue: "AIChE Annual Meeting"
date: 2018-11-01
location: "Pittsburgh PA"
---


This paper discusses approaches to online process optimization, where the objective is usually to minimize an economic cost. In many process control application, traditional real-time optimization (RTO) uses nonlinear steady-state process models to compute the optimal setpoint at steady state operation. The most common approach to RTO is the so-called, two-step model-adaptation approach, where the static model used in the optimization is first updated using measurement data and the updated model is then used to re-compute the new optimal setpoints.

However, traditional RTO faces some challenges, which limits its industrial use, including (in expected order of importance):
* Cost of developing and updating the model structure (offline update of the model),
* Model uncertainty, including uncertain values of disturbances and parameters and structural uncertainty (online update of the model),
* Frequent grade changes, which makes steady-state optimization less relevant,
* Dynamic limitations, including infeasibility due to dynamic constraint violation. 

It would seem that reason 2, 3, and 4 suggests towards dynamic RTO. However, except for processes with frequent grade changes (reason 3), static optimization may be close to economic optimum, at a much lower computational cost. In a recent review paper on current practice of RTO [1], it was noted that the fundamental limiting factor of RTO implementation is the steady-state wait time associated with the online update of the model (reason 2). Since only static models are used, the model adaptation step must be carried out using measurements that corresponds to steady-state operation. If the process is frequently subject to disturbances or if the settling times are too long, this can lead to the plant being operated in transients for significant periods. With the lack of sufficient steady-state measurements, the model is not updated frequently. Consequently, the plant is operated sub-optimally for long periods. Many commercially available steady-state detection methods may also falsely accept transient data as steady state data as demonstrated in [2] using a real industrial example.

On the other hand, dynamic RTO uses dynamic models for model adaptation and the updated dynamic model is used to solve a dynamic nonlinear optimization problem online. However, the main implementation issue with DRTO today is the computational cost, as noted in [3]. 

In this preseantaion, a number of alternative approaches are discussed, given here in the order from most complex (and model-based) to most simple (and data based):

* Economic (nonlinear) model predictive control (EMPC) 
* Dynamic real-time optimization (DRTO) 
* Hybrid RTO - Steady-state RTO with dynamic model update (new method)
* Feedback-based Hybrid RTO (new method)
* Conventional steady-state RTO
* Self-optimizing control
* Extremum seeking control, and similar feedback approaches based on measuring the cost such as NCO tracking and hill-climbing. 

Except possibly for EMPC, the optimizer sends setpoints to a control layer, which could be a PID layer or MPC. Dynamic stability issues (reason4) are then handled by the lower control layer.

In the conventional steady-state RTO, one must wait for the process to reach steady-state before updating the model using "data reconciliation". In the hybrid RTO approach, we solve the same steady-state optimization problem as in traditional Steady-state RTO, but instead of a steady-state model update, we use dynamic model adaptation with the use of transient measurements, for example, using an extended Kalman Filter. This avoids the steady-state wait time.

In the feedback-based hybrid RTO approach, we don't solve the steady-state optimization problem numerically as in conventional RTO, but instead the steady-state gradient is estimated by linearizing the nonlinear dynamic model around the current operating point. The gradient is controlled to zero using standard feedback controllers, for example, a PI-controller. In case of disturbances, the proposed method is able to adjust quickly to the new optimal operation. The advantage of the feedback RTO strategy compared to standard steady-state real-time optimization is that it reaches the optimum much faster and without the need to wait for steady-state to update the model. The advantage compared to dynamic RTO and the closely related economic NMPC, is that the computational cost is much reduced and the tuning is simpler. It is significantly faster than classical extremum-seeking control and does not require the measurement of the cost function and additional process excitation. We compare the performance of different RTO approaches using several simulation case studies. 


References
1.	Darby ML, Nikolaou M, Jones J, Nicholson D. RTO: An overview and assessment of current practice. Journal of Process Control. 2011 Jul 1;21(6):874-84.
2.	Câmara MM, Quelhas AD, Pinto JC. Performance Evaluation of Real Industrial RTO Systems. Processes. 2016 Nov 22;4(4):44.
3.	Campos MC, Teixeira H, Liporace F, Gomes M. Challenges and problems with advanced control and optimization technologies. IFAC Proceedings Volumes. 2009 Jan 1;42(11):1-8.


