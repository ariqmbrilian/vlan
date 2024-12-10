A Virtual Local Area Network (VLAN) is a logical grouping of devices on a network, segmented by function, project team, or organization. VLANs improve network management, security and scalability.

- VLAN
  - Improved Security, Isolate sensitive devices.
  - Simplified Network Management
  - Increased Scalability


Inter VLAN routing allows devices on a different Virtual Local Area Network (VLANs) to communicate with each other.

- Types of Inter VLAN
  - Router on stick
  - Layer 3 Switch

| Device Type | Hostname | Model Number |
|---|---|---|
| Router | ROUTER-1 | 2911 |
| Switch | LT-1 | 2960 |

Topology
![{6F06D241-3005-4F29-9B99-340033D64A4E}](https://github.com/user-attachments/assets/87e29442-c0a7-4661-a724-6cf5c3b4eab9)



Router Configuration
```
hostname ROUTER-1
int g0/0
no sh

int g0/0.10
en do 10
ip add 10.0.10.254 255.255.255.0

int g0/0.20
en do 20
ip add 10.0.20.254 255.255.255.0
```


Switch Configuration
```
hostname LT-1
vlan 10
name Marketing

vlan 20 
name HR

int g0/0
sw mo tr

int ra fa0/1-5
sw mo ac
sw ac vlan 10

int ra fa 0/6-10
sw mo ac
sw ac vlan 20
```
