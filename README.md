Network Topologies Design & Simulation Project

1. Project Description
This project involves the design, simulation, and configuration of a comprehensive enterprise-grade network using Cisco Packet Tracer. It demonstrates proficiency in core networking principles by implementing five fundamental topologies (Bus, Mesh, Star, Ring, Extended Star) and a sophisticated hybrid topology that integrates them. The hybrid network is fully configured with dual-stack (IPv4/IPv6) addressing, VLAN segmentation for security and performance, essential network services ( DHCP), and robust security features, including Switch Port Security to prevent unauthorized access.

The purpose is to create a realistic, scalable, and secure network model that showcases best practices in network design and management.

2. Table of Contents
Project Description
Technologies Used
Installation & Setup
Usage Instructions
Features
Part II: Individual Feature - Switch Port Security Sticky mac address
Contributing
Known Issues & Roadmap
Credits & Acknowledgments
License
Contact

Technologies Used
Simulation Platform: Cisco Packet Tracer 8.x

Network Protocols:

IPv4 & IPv6 (Dual-Stack)

VLAN (IEEE 802.1Q)

Inter-VLAN Routing (Router-on-a-Stick)

DHCP (Dynamic Host Configuration Protocol)

DNS (Domain Name System)

HTTP/HTTPS

Switch Port Security

Device Types: Cisco Routers (1941), Switches (2960), End Devices (PCs, Servers)

5. Installation & Setup
To replicate this project, follow these steps:

Prerequisites:

Install Cisco Packet Tracer (Version 8.0 or higher recommended) from the NetAcad website.

Clone the Repository:

bash
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
Open the Project:

Launch Cisco Packet Tracer.

Open the file Net-Secure-Hybrid-Topology.pkt located in the project's root directory.

Configure Device Credentials (if any):

Username: admin

Password: cisco

Enable Secret: class

6. Usage Instructions
Once the project file is open in Packet Tracer:

Explore Topologies: Navigate to different workspaces to examine the individual Bus, Mesh, Star, Ring, and Extended Star topologies.

Test the Hybrid Network:

Go to the Simulation mode and use the Add Complex PDU tool to send pings or HTTP requests between devices in different VLANs.

Open a PC's desktop tab and use its web browser to navigate to http://www.company.com. The DNS server should resolve this to the web server's IP, demonstrating integrated services.

Verify Connectivity: Use the ping and tracert commands from PC command lines to test connectivity across VLANs and between IPv4/IPv6 devices.

7. Features
Diverse Topologies: Fully documented and configured Bus, Mesh, Star, Ring, and Extended Star networks.

Advanced Hybrid Design: A single, integrated network combining elements of all core topologies for redundancy and scalability.

Dual-Stack Deployment: Simultaneous support for IPv4 and IPv6 addressing across the network.

VLAN Segmentation: Logical separation of network traffic (e.g., Management, HR, Sales VLANs) to enhance security and performance.

Network Services: A central server providing HTTP (web hosting), DNS (domain resolution), and DHCP (dynamic IP assignment).

Comprehensive Security:

Basic Access Control Lists (ACLs) on routers.

Switch Port Security to mitigate Layer 2 threats (Detailed in Part II).

Part II: Individual Feature - Switch Port Security: Sticky MAC Address Configuration
Feature Overview
This individual component focuses on hardening the network at the access layer by implementing Switch Port Security using the Sticky MAC Address learning method. This feature restricts a switch port to only allow a specific, learned MAC address (or a limited number of addresses) to communicate, effectively preventing unauthorized devices from connecting to the network.

Configuration Steps
The following commands were applied to access switch ports connected to end-user devices (e.g., PCs).

Access the Interface:

bash
Switch> enable
Switch# configure terminal
Switch(config)# interface fastethernet 0/1
Set the Interface as an Access Port:

bash
Switch(config-if)# switchport mode access
Enable Port Security:

bash
Switch(config-if)# switchport port-security
Configure Sticky MAC Address Learning:

bash
Switch(config-if)# switchport port-security mac-address sticky
This command tells the switch to dynamically learn and "stick" the MAC address of the currently connected device to the running-configuration.

(Optional) Set Maximum MAC Addresses:

bash
Switch(config-if)# switchport port-security maximum 1
This limits the port to only one MAC address. The default is 1.

Configure Violation Action:

bash
Switch(config-if)# switchport port-security violation shutdown
This defines the response if a security violation occurs. shutdown will error-disable the port, requiring an administrator to re-enable it.

Save the Configuration:

bash
Switch(config-if)# end
Switch# copy running-config startup-config
Crucially, you must save the config. Upon reload, the "sticky" MAC addresses will be saved in the startup-config and will not need to be relearned.

Testing and Verification
Verify the Sticky MAC was Learned:

bash
Switch# show port-security address
This shows the secured MAC addresses that have been sticky-learned.

Test the Security Policy:

Connect a PC to the configured port. Its MAC address will be learned and stored.

Disconnect the authorized PC and connect a different, unauthorized device (like another PC or laptop).

The switch port should immediately go into an err-disabled state, and the unauthorized device will have no connectivity.

Verify the violation with show port-security and show interface status.

10. Credits & Acknowledgments
Cisco Systems: For providing the Cisco Packet Tracer simulation platform.

Course Instructors: For guidance and project requirements.

IETF: For maintaining the RFCs for TCP/IP, VLANs, and other networking standards.

11. License Information
This project is for educational purposes. All configurations and documentation are original work created for this project. The underlying technology is owned by Cisco Systems.

12. Contact Information
Created by [Isaac Thabiso Mawela]

Student ID: [45204136]

University: [North-West University]

Cellphone number:0815264020
