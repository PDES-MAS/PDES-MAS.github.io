---
layout: default
---
# PDES-MAS
## Distributed Simulation of Agent-Based Systems


# Overview

There has been considerable recent interest in agent-based systems , systems based on autonomous software and/or hardware components (agents) which cooperate within an environment to perform some task.  Agent-based systems offer advantages when independently developed components must inter-operate in a heterogeneous environment, e.g. the Internet, and agent-based systems are increasingly being applied in a wide range of areas including telecommunications, business process modelling, computer games, control of mobile robots and military simulations.  While agents offer great promise, adoption of this new technology has been hampered by the limitations of current development tools and methodologies.  Design and implementation remains largely experimental, and experimental approaches are likely to remain important for the foreseeable future.  In this context, simulation has a key role to play in the development of agent-based systems, allowing the agent designer to learn more about the behaviour of the system or to investigate the implications of alternative architectures.

However, the computational requirements of simulations of agent-based systems far exceed the capabilities of conventional sequential von Neumann computer systems.  Each agent is typically a complex system in its own right (e.g.  with sensing, planning, inference etc. capabilities), requiring considerable computational resources, and many agents may be required to investigate the behaviour of the system as a whole or even the behaviour of a single agent.  One solution to this problem is to attempt to exploit the high degree of parallelism inherent in agent-based systems to parallelise the simulation. Decentralised, event driven distributed simulation is particularly suitable or modelling systems with inherent asynchronous parallelism, such as agent-based systems.   However, most work in this area has tended to employ various ad-hoc approaches to parallel simulation, e.g.  distributing the agents over a network of processors interacting via some communication protocol. As a result, the simulations often have relatively poor performance, limiting the nature and scope of the experiments that can be performed.

A key problem in  distributed simulation of agents is the treatment of the agents' environment (the shared state). What is required is a way of efficiently decomposing the shared state to allow both the agents and their environment to be distributed across multiple processors, eliminating the bottlenecks which result from a single centralised environment. Furthermore, this decomposition must be continuously updated as the pattern of  interaction between the agents and their environment changes to ensure that the load remains balanced and performance is not degraded.

PDES-MAS is a framework and a system (simulation kernel)  for the distributed simulation for agent-based systems. PDES-MAS adopts a standard discrete event simulation approach with optimistic synchronization. Each agent is modelled as an Agent Logical Process (ALP) while the shared state is maintained by  a dynamically and transparently reconfigured tree-structured set of additional logical processes, the Communication Logical Processes (CLP), which cluster agent models and shared state.

# Publications
