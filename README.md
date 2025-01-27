[Project Portfolio_Byzantine Fault tolerant Peer to Peer network_AmurushaMuralidharKennedy_22264569 (2).pdf](https://github.com/user-attachments/files/18559417/Project.Portfolio_Byzantine.Fault.tolerant.Peer.to.Peer.network_AmurushaMuralidharKennedy_22264569.2.pdf)
# Byzantine-Fault-Tolerant-Peer-to-Peer-network

README: Byzantine Fault Tolerant Peer-to-Peer Network
Overview
This repository contains the implementation and results of a Byzantine Fault Tolerant Peer-to-Peer Network. The project focuses on designing a decentralized network prototype capable of tolerating Byzantine faults through the Practical Byzantine Fault Tolerance (PBFT) consensus algorithm. The implementation explores the efficiency of various routing protocols under fault conditions, providing insights into the scalability and resilience of such networks.
Key Features
- Implementation of PBFT consensus algorithm in a peer-to-peer network.
- Integration of Gossip-Based Routing, AODV, and DSR protocols.
- Performance testing under various network sizes and fault levels.
- Evaluation of metrics such as throughput, transmission delay, packet loss, and packet delivery ratio.
Methodology
The network was simulated using the Network Simulator 3 (NS3), with PBFT integrated into three distinct routing protocols: Gossip-Based Routing, Ad Hoc On-Demand Distance Vector (AODV), and Dynamic Source Routing (DSR). Faults were introduced to analyze network behavior under various scenarios.
Results
The following results were obtained from simulations and visualized using Gnuplot:
- **Throughput**: Gossip protocol achieved the highest throughput of 1.8 Mbps under fault conditions.
- **Transmission Delay**: Gossip protocol exhibited the lowest average delay of 1.25 ms.
- **Packet Loss**: Gossip protocol demonstrated resilience with lower packet loss percentages compared to AODV and DSR.
- **Packet Delivery Ratio**: Gossip protocol maintained a higher PDR, even under extreme fault scenarios.
Installation and Usage
1. Clone this repository.
2. Install Network Simulator 3 (NS3) version 3.25 or later.
3. Compile the provided C++ code within the NS3 environment.
4. Use the included simulation scripts to run tests and analyze results.
Repository Structure
- **/src**: Contains the C++ source code for PBFT and routing protocols.
- **/results**: Gnuplot graphs visualizing network performance.
- **/docs**: Documentation and appendices.

