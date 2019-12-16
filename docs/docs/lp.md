---
title: Logical Process
summary: Introduction to LPs
---

# Logical Process

## class `Alp`

ALP (Agent Logical Process) is where the agent runs. Typically, an ALP would contain one or more agents. 
This could be configured when writing your own simulation. Agents inside ALPs are actually threads rather than MPI processes.
But still, they runs in a asynchronous, non-blocking way. 

## class `Clp`

CLP (Communication Logical Process) is where the shared states are stored and all messages sent by agent will pass through one or more CLPs.

