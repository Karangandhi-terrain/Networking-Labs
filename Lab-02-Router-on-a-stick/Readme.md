# Network Fundamentals Lab 2: VLANs and Router-on-a-Stick

This is my second network lab project. I built this to practice network segmentation and inter-VLAN routing. The goal was to separate broadcast domains using VLANs and configure a single router interface to handle the routing between them using 802.1Q encapsulation.

## What This Lab Covers
This project demonstrates Layer 2 segmentation and how to securely pass traffic between isolated networks. I focused on configuring the switch to handle multiple VLANs and setting up the router to act as the gateway for both.

* Creation and naming of multiple VLANs
* Assigning switchports to specific access VLANs
* Configuring an 802.1Q trunk link between the switch and router
* Setting up router subinterfaces for inter-VLAN routing (Router-on-a-Stick)
* Testing ICMP connectivity across different subnets

## Network Topology
Here is the layout of the network I built. It consists of a core router connected to a single access switch via a trunk link, serving PCs in two different departments.

![Network Topology](Lab%202%20Topology)

## IP Addressing and VLAN Table
Below is the reference guide for the network addressing and VLAN assignments used in this lab.

| Device | Interface | VLAN | IP Address | Subnet Mask | Default Gateway |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Router** | G0/0.10 | 10 | 20.10.10.1 | 255.255.255.0 | N/A |
| **Router** | G0/0.20 | 20 | 20.10.20.1 | 255.255.255.0 | N/A |
| **PC1** | fa0/1 | 10 (Finance) | 20.10.10.10 | 255.255.255.0 | 20.10.10.1 |
| **PC2** | fa0/2 | 20 (Marketing) | 20.10.20.10 | 255.255.255.0 | 20.10.20.1 |
| **PC3** | fa0/3 | 10 (Finance) | 20.10.10.11 | 255.255.255.0 | 20.10.10.1 |

## Lab Access Credentials
If you download the `.pkt` simulation file to explore the configurations in Cisco Packet Tracer, use the following credentials to access the devices:

* **Console Password:** Test@12345
* **Privileged EXEC (Enable):** a1b2c3d4
* **SSH Username:** admin
* **SSH Password:** login@12345

## How to Run It
If you want to test this lab yourself, download the `.pkt` file and open it in Cisco Packet Tracer. You can open the command prompt on any of the PCs to test ping connectivity to devices in the other VLAN to verify the routing is working. You can also view the raw configuration files exported in this folder to see the subinterface and trunking commands.
