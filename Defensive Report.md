# Blue Team: Summary of Operations

## Table of Contents
- Network Topology
- Description of Targets
- Monitoring the Targets
- Patterns of Traffic & Behavior
- Suggestions for Going Further

### Network Topology
![Final Project Network_Topology](/Network_Topology.JPG)

The following machines were identified on the network:

- Kali
  - **Operating System**: Linux 5.4.0-kali3-amd64
  - **Purpose**: The machine from where we attack the target 
  - **IP Address**: 192.168.1.90
- ELK
  - **Operating System**: Linux 4.15.0-99-generic
  - **Purpose**: The machine used for monitoring the target with Kibana logging events
  - **IP Address**: 192.168.1.100
- Capstone
  - **Operating System**: Ubuntu 18.04
  - **Purpose**: The machine hosting FileBeat, MetricBeat, and PacketBeat
  - **IP Address**: 192.168.1.115
- Target 1
  - **Operating System**: Linux 3.16.0-6-amd64
  - **Purpose**: Web Server used as a target for attacks
  - **IP Address**: 192.168.1.110
- ML-RefVm-684427
  - **Operating System**: Windows 10
  - **Purpose**: Hosts the Hyper-V manager which containers the other VMs. Also used to view Kibana.
  - **IP Address**: 192.168.1.1

### Description of Targets

The target of this attack was: `Target 1` with IP Address: 192.168.1.110.

Target 1 is an Apache web server and has SSH enabled, so ports 80 and 22 are possible ports of entry for attackers. As such, the following alerts have been implemented:

### Monitoring the Targets

Traffic to these services should be carefully monitored. To this end, we have implemented the alerts below:

#### Excessive HTTP Errors
Excessive HTTP Errors is implemented as follows:
  - **Metric**: http.response.status_code
  - **Threshold**: above 400 in last 5 minutes
  - **Vulnerability Mitigated**: Brute force attack 
  - **Reliability**: ?

#### CPU Usage Monitor
CPU Usage Monitor is implemented as follows:
  - **Metric**: system.process.cpu.total.pct
  - **Threshold**: over 0.5 in the last 5 minutes
  - **Vulnerability Mitigated**: DoS attack / Brute force attack
  - **Reliability**: ?

#### HTTP request size monitor
HTTP request size monitor is implemented as follows:
  - **Metric**: http.request.bytes
  - **Threshold**: is above 3500 for the last 1 min
  - **Vulnerability Mitigated**: Potential file upload/download of files 
  - **Reliability**: ?

