# Network topology-based risk calculations for inventory management

This repository contains research materials related to the paper:

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
- Directed edges represent dependency/precedence relationships.  
- Node failures (unavailability) can propagate downstream and affect product/service levels.

### 2) Structural consequence of unavailability
We quantify the structural impact of removing a component (node) from the assembly network using **robustness metrics based on Jensen–Shannon divergence (JSD)**. This captures how much the structural or functional characteristics of the network change when a component becomes unavailable.

### 3) Component failure probabilities
Component-level failure probabilities are derived from factors such as:
- **Stock availability**
- **Procurement reliability**
- **Manufacturability**
- **Back-propagation of availability** through predecessor chains (upstream dependencies)

### 4) Node-level risk scores and inventory allocation
By combining:
- Consequence (topology-based vulnerability/robustness impact), and  
- Probability (availability/failure likelihood),  

we compute **node-level risk scores** and apply a **greedy, risk-based inventory allocation algorithm** that prioritizes components with the highest contribution to system-level vulnerability.

## Code availability

The full implementation of the proposed framework will be made publicly available upon publication of the associated paper.  

If you are interested in the methodology or would like early access for academic collaboration purposes, please feel free to contact the authors.
