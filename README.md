# sdn-project
# SDN Flow Rule Timeout Manager

## Project Overview

**Problem Statement:**  
Implement timeout-based flow rule management in an SDN environment using Mininet and an OpenFlow controller (POX). The controller must install flow rules with an idle timeout, automatically remove expired rules, and demonstrate the full rule lifecycle (install → use → expire → re-install).

**Why this matters:**  
Flow tables in switches have limited capacity. Idle timeouts prevent stale flows from consuming memory and ensure that only active flows remain in the hardware. This project shows how an SDN controller can manage flow timeouts effectively.

**Technologies used:**  
- Mininet (network emulator)  
- POX controller (OpenFlow 1.0)  
- OpenFlow protocol  
- Tools: `ovs-ofctl`, `ping`, `iperf`

---

## Topology
h1

|

s1

|

h2


- **Switch:** s1 (Open vSwitch)  
- **Hosts:** h1 (10.0.0.1), h2 (10.0.0.2)  
- **Controller:** POX running `flow_timeout_manager.py` (remote, IP 127.0.0.1, port 6633)

**Why this topology:**  
Simple enough to clearly observe flow rule installation and timeout. Two hosts allow basic ping and iperf tests.

---

## Setup and Execution

### Prerequisites
- Ubuntu 20.04/22.04 (or Mininet VM)  
- Python 3.8+  
- Mininet (`sudo apt install mininet`)  
- POX (cloned from GitHub)  
- Open vSwitch (comes with Mininet)

### Installation Steps

1. **Clone POX**  
   ```bash
   git clone http://github.com/noxrepo/pox ~/pox
   cd ~/pox
