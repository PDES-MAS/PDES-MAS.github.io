---
title: Agent Programming Interface
summary: Guide to use the agent programming interface in PDES-MAS.
---

# Agent Programming Interface

## class `Simulation` 

### method `Construct`
Construct the simulation, with specifying number of CLPs, number of ALPs, and simulation start and end time.

This is the step where MPI processes are created and forked from main process. After that, all codes executing 
will be at different MPI processes.
### method `attach_alp_to_clp`
Attaches an ALP to a leaf CLP. This is typically controlled by users. If an ALP is not attached to a CLP, it will not be 
able to communicate to other process, and the simulation will exit with errors after it starts.
### method `preload_variable`
Pre-loads variables into the shared states. Since PDES-MAS do not support dynamically adding or removing variables after the simulation 
has been started, all variables needed in the simulation must be initialised in advance using this method. 

The variable types supported are: integers, floats, strings, and 2D points (with two integers x, y).
### method `Initialise`
After setting the attachment between ALPs and CLPs, and preloading all variables needed, the `Initialise` method 
initialises every MPI process as what it should be, ALP or CLP. It also used the data collected from previous user settings 
to initialise variables inside CLPs.
### method `Run`
Start actually running the simulation. This includes starting the LP and running all threads needed inside it, such as message 
polling and sending. Note that agent threads is not started here. 
### method `Finalise`
The method executed when ending the simulation. This could either collect the logs, or just exit.
### method `add_agent`
Adds agents to a ALP. When the method is called on a CLP process, nothing will happen.


## class `Agent` 
The agent inside ALPs are actually threads running concurrently. To program a agent, simply override the method 
`Cycle` in your own agent class inheriting the `Agent` class. 
### method `Cycle`
This is the main loop agent is going to execute. Inside this method, you need to use the data accessing methods provided 
by our agent programming interface to define the behaviour of your own agent.
### method `SendGVTMessage`
This methods initiates GVT calculation across the whole system. Typically this is automatically controlled by the system 
and users won't need to touch this. If the GVT synchronization is too often, this may cause significant overhead thus slowing 
down the simulation.
### method `time_wrap`
This method is used to step timestamps when user is not doing anything in a given time period. Since PDES-MAS itself is event-driven, 
this method will just increase the LVT of agent.
### method `ReadInt`
Read an integer SSV.
### method `ReadDouble`
Read a double SSV.
### method `ReadPoint`
Read a 2D point SSV.
### method `ReadString`
Read a string SSV.
### method `WriteInt`
Modify an integer SSV.
### method `WriteDouble`
Modify a double SSV.

### method `WritePoint`
Modify a 2D point SSV.

### method `WriteString`
Modify a string SSV.
### method `RangeQueryPoint`
Perform range query in a given 2D rectangle range. Returns a list of point SSVs inside that range.
### method `ReadPrivateInt`
Read an integer agent local variable.

### method `ReadPrivateDouble`
Read a double agent local variable.

### method `ReadPrivatePoint`
Read a 2D point agent local variable.

### method `ReadPrivateString`
Read a string agent local variable.

### method `WritePrivateInt`
Modify an integer agent local variable.

### method `WritePrivateDouble`
Modify a double agent local variable.

### method `WritePrivatePoint`
Modify a 2D point agent local variable.

### method `WritePrivateString`
Modify a string agent local variable.




