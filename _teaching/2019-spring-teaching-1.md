---
title: "Numerical optimization"
collection: teaching
type: "Lecturer"
permalink: /teaching/2019-spring-teaching-1
venue: "UFRJ-COPPE"
date: 2019-04-29
location: "Rio de Janeiro, Brazil"
---

Invited short course on numerical optimization given at the Federal University of Rio de Janerio (UFRJ) in Spring 2019.

The aim of this course is to provide basic theory behind process optimization, such that these tools may be applied to subsea production and processing. This course discusses various approaches to online process optimization, where the objective is usually to minimize an economic cost function. Since most processes are nonlinear in nature, a part of this course will cover nonlinear programming in the context of optimal control. 
The first part of the course starts with the basic overview of optimization and focuses on steady-state nonlinear optimization. The course then progresses to cover dynamic optimization problems using ordinary differential equations. In this part, various successful discretization techniques such as multiple shooting and direct collation will be covered, such that it gives the students a clear picture of to approach an optimal control problem in a continuous form. The course will further give an understanding on how to use the dynamic optimization problem for solving model predictive control problems.
The course will be supplemented with hands-on exercise using simple production optimization problems as an example. The exercises will be delivered using CasADi toolbox with MATLAB interface, which is an open source tool. The exercises along with the solutions will also be provided to the students. The course is planned to be a full day course, i.e. morning and afternoon sessions. 

[Introduction](http://folk.ntnu.no/dineshk/Courses/UFRJ_NumOpt/Introduction.pdf)

Course Syllabus 

* [Lecture 1: Introduction to optimization and preliminaries](http://folk.ntnu.no/dineshk/Courses/UFRJ_NumOpt/Lecture%201.pdf)
  * Introduction, preliminaries and notations
  *	General optimization problem
  *	Different types of optimization problem and solvers

* [Lecture 2: Understanding the KKT conditions](http://folk.ntnu.no/dineshk/Courses/UFRJ_NumOpt/Lecture2.pdf)
  *	Unconstrained optimization
  *	Constrained optimization and active constraints
  *	Formalizing the KKT conditions

* [Lecture 3: Steady state optimization](http://folk.ntnu.no/dineshk/Courses/UFRJ_NumOpt/Lecture3.pdf)
  *	Developing ODE and DAE models
  *	Steady state optimization 
  *	With hands-on demo using CasADi 

* [Lecture 4: Dynamic optimization](http://folk.ntnu.no/dineshk/Courses/UFRJ_NumOpt/Lecture4.pdf), [Part2](http://folk.ntnu.no/dineshk/Courses/UFRJ_NumOpt/Lecture4_2.pdf)
  *	Direct and indirect methods
  *	Single shooting and multiple shooting
  *	Direct collocation
  *	Converting FHOCP to a standard NLP problem
  *	With hands on demo using CasADi
  
* Lecture 5: Model Predictive control 
  *	Linear MPC
  *	Nonlinear MPC
  *	Economic MPC
  
* Lecture 6: MPC under uncertainty 
  *	Formulating a linear MPC
  *	With hands on demo using CasADi
  *	Short review and introduction of the recent advances in MPC under uncertainty
  
  [Exercise 1](http://folk.ntnu.no/dineshk/Courses/UFRJ_NumOpt/Ex1.pdf)
 [Exercise 2](http://folk.ntnu.no/dineshk/Courses/UFRJ_NumOpt/Ex2.pdf)
