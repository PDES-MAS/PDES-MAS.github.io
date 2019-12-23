---
layout: default
---


# Overview and Rationale
Recent years have witnessed an explosion of interest in complex systems, systems that involve non-linear interactions between large numbers of components. Depending on the domain, these components can be physical particles, biological entities, software elements, hardware devices or social entities. The complexity of such systems renders simulation modelling the only viable method to study their properties and analyse their behaviour.  In contrast, to the predominant approach to model such systems at the macro-level using numerical methods there has been an increasing trend to model complex systems at the micro-level and study their properties without making any a-priori assumptions about their aggregate emergent behaviour. 

Multi-Agent Systems (MAS) and individual-based models have emerged as a key paradigm for modelling complex systems. As MAS models are being applied for the analysis of ever larger complex adaptive System-of-Systems, distributed simulation has emerged as the only viable approach to deal with their size and scale. However conventional distributed simulation approaches are not well suited for MAS simulations. The fundamental problem is that MAS models are by nature dynamic, non-deterministic and data-centric, it is therefore difficult to define an a-priori parallelisation and partition strategy. This is exacerbated by the compute-centric architecture of existing HPC systems. Shifting from compute-centric to more data-centric systems (hardware and software) for big data problems is at the heart of design efforts by major IT vendors at different levels, from integrated photonics and active memory to graph databases. The need for co-design is strongly recognised and agent-based models present unique challenges and opportunities in this direction.

PDES-MAS aims to address these challenges. PDES-MAS is a framework and a distributed simulation engine for multi Agent-based system models. 

# The PDES-MAS Philosophy
The PDES-MAS framework is based on PDES paradigm, where a simulation model is divided into a network of concurrently executing Logical Processes (LPs), each maintaining and processing the disjointed state spaces of the model. Two types of LP exist in a PDES-MAS simulation. Agent Logical Processes (ALPs) are responsible for modelling the behaviour of the agents in the MAS. This includes the processing of sense data, the modelling of behavioural processes (such as planning or rule set evaluation) and the generation of the new actions. ALPs store only private state variables while the shared state (public variables, including publicly accessible attributes of agents) are distributed over and managed by a tree-like network of server LPs known as Communication Logical Processes (CLPs). CLPs essentially implement a space-time Distributed Shared Memory (DSM) model whereby agents interact with their environment and communicate via accessing public variables. In response to the sensing and acting of agents in the simulation, ALPs perform reads and writes on Shared-State Variables (SSVs) in the system.  The primary philosophy of PDES-MAS is to provide multiple ALPs concurrent access to a set of SSVs in a scalable manner by a automatic, dynamic reconfiguration of the CLP tree to reﬂect the interaction patterns between the agents and their environment. 
![](/assets/images/pdesmas/topology.svg)

# Novelty and Contributions
PDES-MAS represents research efforts and investments of almost 20 years.  PDES-MAS has been a mould-breaking system that has made innovative contributions along different strands:

1. **Distributed Simulation of MAS:** PDES-MAS has been  one of the earliest efforts that pioneered the field of distributed simulation of MAS models and developed a generic distributed simulation engine specific for MAS. 
2. **Event-Driven Simulation of Agents:** Contrary to the vast majority of the simulation engines for agent models that are time-driven, PDES-MAS supports a purely event-driven modelling approach.  
3. **Optimistic Synchronisation for MAS.** PDES-MAS has been the first system to investigate optimistic synchronisation for MAS distributed simulations.
4. **Data-Centric Simulation, Linking Models to Data:** PDES-MAS has demonstrated a method for accessing data from within a simulation using different forms of queries. It has been the first to address the problem of synchronised range queries. 
5. **Space-Time Memory:** PDES-MAS implements a synchronised Distributed Shared Memory approach for state distribution and access. Contrary to most systems that utilise proxies and push methods for consistency, PDES-MAS proposes a pull approach without the use of proxies. 
6. **Distributed Virtual Environments:** PDES-MAS has been the first system to address the problems of state partition, interest management and synchronisation in an integrated, adaptive and fully transparent manner. 




