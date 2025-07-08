# Hotel-Network Simulation
This project is a Cisco Packet Tracer lab that simulates a multi-floor hotel network with three floors (1st, 2nd, and 3rd). Each floor has its own router and switch to support departmental VLAN segmentation, inter-VLAN routing, dynamic IP addressing via DHCP, and secure remote access using SSH. The network uses OSPF as the dynamic routing protocol to enable communication between all floors.

# Network Topology
![image](https://github.com/user-attachments/assets/00f58826-a4e5-4d49-85dc-c3c82a7ffa5d)

## The hotel network is divided into three floors:

* 1st Floor Router and Switch

* 2nd Floor Router and Switch

* 3rd Floor Router and Switch

Routers on each floor connect to each other via serial links.

VLANs are configured per department on each floor’s switch.

DHCP services assign IP addresses dynamically.

OSPF is configured on all routers for inter-floor routing.

SSH is set up for secure management access.

## Router Configuration
The first step was configuring the serial interfaces and the clock rate on the Routers. Below is the commands done on the 3rd floor's router. This step was repeated for the 1st and 2nd floors to bring up their serial interfaces.

![image](https://github.com/user-attachments/assets/2748a1b3-b641-4a4e-a413-43ce3e4f0806)

## VLAN Configuration on Switches
Each floor switch was configured with VLANs for its departments. Below is the example configuration on the 2nd Floor Switch. The same procedure was repeated for the 1st and 3rd Floor Switches.

![image](https://github.com/user-attachments/assets/3d0f658d-8ba2-494d-8b74-81055546d1b9)

## Subinterface Creation and VLAN Tagging
To enable inter-VLAN routing on each floor, subinterfaces were created on each router using 802.1Q tagging. 

### Floor 1
![image](https://github.com/user-attachments/assets/4c84cc4a-a28d-472a-8cec-e91bf8112142)

### FLoor 2
![image](https://github.com/user-attachments/assets/de7fc4e6-e9c3-41dc-a63d-218e0ca657bd)

### Floor 3
![image](https://github.com/user-attachments/assets/af11bbf2-ae71-4819-ab05-404bc1d9d009)


## OSPF Routing Configuration
To enable communication between different floors, OSPF was configured on all routers. This ensured dynamic route sharing and connectivity throughout the hotel network.
### Floor 1 and 2:
![image](https://github.com/user-attachments/assets/55887170-b8d0-4c0a-85a2-83daffe4549d)

### Floor 3
![image](https://github.com/user-attachments/assets/445f0be0-0002-49b0-b3a3-9a1b1eb6e7c3)

## SSH Configuration
Secure remote access was enabled on all routers using SSH. Below is the configuration on the 1st Floor Router, with similar steps repeated on the other floors.
![image](https://github.com/user-attachments/assets/046f3bcc-1ba7-4ccc-84fb-28e016742253)


### SSH Connectivity Test
SSH from IT PC (3rd Floor) into 2nd Floor Router:
![image](https://github.com/user-attachments/assets/e647c510-204b-48a3-80f0-e8afc5497d8e)

SSH from IT PC (3rd Floor) into 1st Floor Router:
![image](https://github.com/user-attachments/assets/2a4ab7a4-c100-420e-b6da-e45adc386e02)

## Switch Port Security
Port security was configured on interface Fa0/2 of the 3rd Floor Switch to limit unauthorized access.
![image](https://github.com/user-attachments/assets/321738f6-3b9e-408a-90ab-1dd5a340b62b)

# Connectivity Tests
### Ping Tests Conducted:

### PC4 in HR (VLAN 40) to PC7 in Admin Department (VLAN 20)
![image](https://github.com/user-attachments/assets/4d288f13-04ac-4281-9d3c-e3d981d01b7f)

### PC2 in Reception (VLAN 80) to PC3 in Finance (VLAN 50) 
![image](https://github.com/user-attachments/assets/3dc83bfe-aa79-4bb4-89ef-2b431128c250)

Note: Since this was the first time initiating a ping from each device, the initial request timed out in both scenarios. This occurred because the ARP (Address Resolution Protocol) process had not yet completed, requiring the devices to resolve MAC addresses before successful communication could occur.

# Summary & Takeaways
Through this project, I strengthened my skills in:
* Designing multi-floor network topologies using routers and switches
* VLAN creation and trunking with 802.1Q tagging
* Configuring inter-VLAN routing on routers with subinterfaces
* Setting up DHCP services for dynamic IP assignment
* Implementing OSPF for dynamic routing across floors
* Securing network devices with SSH access
* Applying port security on switch interfaces
* Troubleshooting connectivity and verifying configurations

See packet tracer file in repository for the Hotel file
