---
layout: default
---


# Overview
PDES-MAS is a framework and a system (simulation kernel)  for the distributed simulation for agent-based systems. 
PDES-MAS adopts a standard discrete event simulation approach with optimistic synchronization. 
Each agent is modelled as an Agent Logical Process (ALP) while the shared state is maintained by a 
dynamically and transparently reconfigured tree-structured set of additional logical processes, 
the Communication Logical Processes (CLP), which cluster agent models and shared state.

![](/assets/images/pdesmas/topology.svg)


There has been considerable recent interest in agent-based systems, systems based on autonomous software and/or hardware 
components (agents) which cooperate within an environment to perform some task. 
Agent-based systems offer advantages when independently developed components must inter-operate in a heterogeneous 
environment, e.g. the Internet, and agent-based systems are increasingly being applied in a wide range of areas including 
telecommunications, business process modelling, computer games, control of mobile robots and military simulations. 
While agents offer great promise, adoption of this new technology has been hampered by the limitations of current 
development tools and methodologies.  Design and implementation remains largely experimental, 
and experimental approaches are likely to remain important for the foreseeable future. 
In this context, simulation has a key role to play in the development of agent-based systems, 
allowing the agent designer to learn more about the behaviour of the system or to investigate 
the implications of alternative architectures.

However, the computational requirements of simulations of agent-based systems far exceed the capabilities of conventional 
sequential von Neumann computer systems.  Each agent is typically a complex system in its own right 
(e.g.  with sensing, planning, inference etc. capabilities), requiring considerable computational resources, 
and many agents may be required to investigate the behaviour of the system as a whole or even the behaviour of 
a single agent.  One solution to this problem is to attempt to exploit the high degree of parallelism inherent 
in agent-based systems to parallelise the simulation. Decentralised, event driven distributed simulation is 
particularly suitable or modelling systems with inherent asynchronous parallelism, such as agent-based systems. 
However, most work in this area has tended to employ various ad-hoc approaches to parallel simulation, e.g. 
distributing the agents over a network of processors interacting via some communication protocol. As a result, 
the simulations often have relatively poor performance, limiting the nature and scope of the experiments that 
can be performed.

A key problem in distributed simulation of agents is the treatment of the agents' environment (the shared state). 
What is required is a way of efficiently decomposing the shared state to allow both the agents and their environment 
to be distributed across multiple processors, eliminating the bottlenecks which result from a single centralised 
environment. Furthermore, this decomposition must be continuously updated as the pattern of 
interaction between the agents and their environment changes to ensure that the load remains balanced and performance 
is not degraded.


# How to use

You can follow the user guide in [Getting Started](/getting_started/)

# Publications
- M. Lees, B. Logan, G. Theodoropoulos, "Analysing Probabilistically Constrained Optimism", Concurrency and Computation: Practice and Experience Journal,  special issue on "Distributed  Simulation, Virtual Environments and Real Time Applications, to appear

- D. Chen, R.  Ewald, G. Theodoropoulos, R. Minson, T Oguara,  M. Lees, B. Logan, and A. Uhrmacher "Data Access in  Distributed Simulation of Complex Systems",  Journal of Systems and Software, Elsevier,  Volume 81, Issue 12, December 2008, Pages 2345-2360. DOI:10.1016/j.jss.2008.04.041   

- M. Lees, B. Logan, G. Theodoropoulos  "Using Access Patterns to Analyze the Performance of Optimistic Synchronization Algorithms in Simulations of MAS", Transactions of the Society for Computer Simulation International, Transactions of the Society for Computer Simulation International, Volume 84, Number 10/11,  481-492. ISSN: 0037-549

- M. Lees, B. Logan, D. Chen, T. Oguara ,G. Theodoropoulos, "Analysing Probabilistically Constrained Optimism", 10th IEEE International Symposium on Distributed Simulation and Real Time Applications (DS-RT 2006) October 2-6, 2006, Torremolinos, Malaga, Spain. 8 pages

- M. Lees, B. Logan, D. Chen, T. Oguara G. Theodoropoulos "Predicting the Performance of Optimistic Simulations of Multi-Agent Systems", the 20th ACM/IEEE/SCS Workshop on Principles of Advanced and Distributed Simulation (PADS 2006), May 23-26, 2006, Raffles Hotel, Singapore.  8 pages. Nominated for Best paper Award

- R.  Ewald, D. Chen, G. Theodoropoulos, M. Lees, B. Logan, T Oguara and A. Uhrmacher "Performance Analysis on Shared Data Accessing Algorithms for Distributed Simulation of Multi Agent Systems", the 20th  ACM/IEEE/SCS Workshop on Principles of Advanced and Distributed Simulation (PADS 2006), May 23 - 26, 2006, Raffles Hotel, Singapore.

- M. Lees, B. Logan, D. Chen, T. Oguara G. Theodoropoulos "Decision-Theoretic Throttling for Optimistic Simulations of Multi-Agent Systems", The 9-th IEEE International Symposium on Distributed Simulation and Real Time Applications (DS-RT 2005), October 10-12, 2005 Montreal, Qc. Canada.  ISBN: 0-7695-2462-1, Pages: 171-178 

- T. Oguara, D. Chen, G. Theodoropoulos, M. Lees, B. Logan, "An Adaptive Load Management Mechanism for Distributed Simulation of Multi-agent Systems", The 9-th IEEE International Symposium on Distributed Simulation  and Real Time Applications (DS-RT 2005), October 10-12, 2005 Montreal, Qc. Canada.  ISBN: 0-7695-2462-1, Pages: 179-186

- M.Lees, B.Logan, R.Minson, T. Oguara, G. Theodoropoulos "Modelling Environments for Distributed Simulation", 1st International Workshop on Environments for Multiagent Systems (E4MAS), in conjunction with the 3rd International Joint Conference on Autonomous Agents and Multi-Agent Systems (AAMAS04), New York, 19-23 July 2004. Lecture Notes on Artificial Intelligence (LNAI), No: 3374, 2004.  Springer, ISBN 3-540-24575-8, Pages: 150-167.

- Lees, M., Logan, B., Theodoropoulos, G., "Time Windows in Multi-Agent Distributed Simulation", Modelling and Simulation of Distributed Systems and Networks, 5th European Simulation Congress (EUROSIM04, European Simulation Societies Federation), 6-10 September 2004, ESIEE, Cite Descartes, Marne la Vallee, France. ISBN 3-901608-28-1. 

- M.Lees, B. Logan, R.Minson, T. Oguara, G. Theodoropoulos, "Distributed Simulation of MAS", Joint Workshop on Multi-Agent and Multi-Agent-Based Simulation (MAMABS04), in conjunction with the 3rd International Joint Conference on Autonomous Agents and Multi-Agent Systems (AAMAS04), New York, 19-23 July 2004. Lecture Notes on Artifical Intelligence (LNAI), No: 3415, 2004.  Springer, ISBN 3-540-25262-2, Pages:  25-36.

- Michael Lees, Brian Logan, and Georgios Theodoropoulos (2003). "Adaptive Optimistic Synchronisation for Multi-Agent Simulation." Proceedings of the 17th   European Simulation Multiconference (ESM 2003) (pp. 77-82). 

- Theodoropoulos, G., Logan, B., " An Approach for Interest Management And Dynamic Load Balancing In Distributed Simulations " , 2001 European Simulation Interoperability Workshop , 2001 Euro-SIW, University of Westminster, Harrow Campus, Harrow, Middlesex, United Kingdom, June 25-27, 2001.

- Logan, B., Theodoropoulos, G. " The Distributed Simulation of Agent-Based Systems", IEEE Proceedings Journal, Special Issue on Agent-Oriented Software Approaches in Distributed Modelling and Simulation, February 2001.

- Theodoropoulos, G., Logan, B., " A Unified Framework for the Interest Management and Dynamic Load Balancing in Distributed Simulation " Proceedings of 12th European Simulation Symposium (ESS?2000),  28-30 September 2000,  University of Hamburg, Hamburg, Germany, pp. 111-115, Society for Computer Simulation International, ISBN 1-56555-190-7, editors: Dietmar Moeller.

- Logan, B., Theodoropoulos, G., " Dynamic Interest Management in the Distributed Simulation of Agent-Based Systems", Proceedings of 10th AI, Simulation and Planning Conference, Sheraton Hotel, Tucson, Arizona, March 6-8 2000, pp. 45-50, Society for Computer Simulation International, ISBN: 1-56555-194-X, H. Sarjoughian, F. Cellier, Michael Marefat, J. Rozenblit (RAE2001)

- Theodoropoulos, G., Logan, B., " A Framework for the Distributed Simulation of Agent-Based Systems", 13th European Simulation Multiconference (ESM99), Warsaw, Poland, June 1-4, 1999. pp. 58-65, Society for Computer Simulation International, ISBN 1-56555-171-0 editor: H. Szczerbicka

Theodoropoulos, G., Logan, B., "Distributed Simulation of Agent-based Systems", Proceedings of  3rd Euro-conference on Parallel and Distributed Computing for Computational Mechanics", Weimar, 20-25 March 1999. pp. 147-153, editor: B.H.V.Topping, CIVIL-COMP-PRESS, 10 Saxe-Coburg Place, Edinburgh, EH3 5BR, UK, ISBN: 0-948749-59-8.