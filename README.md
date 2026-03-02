# Network topology-based risk calculations for inventory management

This repository contains research code and materials for the paper:

**Network topology-based risk calculations for inventory management**  
László Gadár, Tímea Czvetkó, János Abonyi, Alex Kummer  
HUN-REN-PE Complex Systems Monitoring Research Group, Department of Process Engineering, University of Pannonia

## Overview

Effective inventory management in complex assembly systems must account for (1) structural dependencies between components and (2) uncertainty in material availability. This project introduces a **network-topology-based risk assessment framework** that integrates:

- **Structural vulnerability analysis** of multi-product assembly networks
- **Probabilistic modeling** of component/material availability
- A **risk-based (greedy) inventory allocation** strategy prioritizing components that most improve system resilience

Assembly processes are represented as **directed graphs**, where component unavailability can propagate through hierarchical dependencies.

## Key ideas

### 1) Assembly as a directed graph
- Nodes represent components/materials/subassemblies.
- Directed edges represent dependency/precedence (i.e., what is needed to assemble what).
- Node failures (unavailability) can propagate downstream and affect product/service levels.

### 2) Structural consequence of unavailability
We quantify the structural impact of removing a component (node) from the assembly network using **robustness metrics based on Jensen–Shannon divergence (JSD)**. Intuitively, this measures how much the network’s “structure” or functional connectivity changes when a component becomes unavailable.

### 3) Component failure probabilities
Component-level failure probabilities are derived from factors such as:
- **Stock availability**
- **Procurement reliability**
- **Manufacturability**
- **Back-propagation of availability** through predecessor chains (upstream dependencies)

### 4) Node-level risk scores + inventory allocation
By combining:
- consequence (topology-based vulnerability/robustness impact), and
- probability (availability/failure likelihood),

we compute **node-level risk scores** and apply a **greedy, risk-based inventory allocation algorithm** that prioritizes components with the highest contribution to system-level vulnerability.

