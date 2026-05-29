# Network Fundamentals Lab 1: Basic Routing

This is my first complete network lab project. I built this to practice configuring basic routing, switching, and network connectivity from scratch. The goal was to take a standard topology and get everything communicating securely and properly.

## What This Lab Covers
This project demonstrates core networking concepts and production-ready configuration practices. I focused on setting up the fundamental infrastructure that would support a small office environment.

* Initial device configuration like hostnames and interface descriptions
* Securing the console port and privileged mode
* Disabling DNS lookup to prevent console hangs
* Generating RSA crypto keys and configuring SSH for secure remote access
* Assigning IPv4 addresses to router interfaces and end devices
* Testing connectivity using ping and SSH

## Network Topology
Here is the logical layout of the network I built. It consists of a core Cisco ISR4331 router, two access switches, and several PCs separated into two different subnets.

![Network Topology](topology.png)

## IP Addressing Table
Below is the reference guide for the network addressing used in this lab.

| Device | Interface | IP Address | Subnet Mask | Default Gateway |
| :---   | :---      | :---       | :---        | :---            |
| **R1-Core** | G0/0/0    | 10.1.1.1   | 255.255.255.0| N/A       |
| **R1-Core** | G0/0/1 | 10.2.2.1 | 255.255.255.0 | N/A           |
| **PC0** | NIC | 10.1.1.10 | 255.255.255.0 |            10.1.1.1 |
| **PC1** | NIC | 10.1.1.20 | 255.255.255.0 |            10.1.1.1 |
| **PC2** | NIC | 10.2.2.10 | 255.255.255.0 |            10.2.2.1 |
| **PC3** | NIC | 10.2.2.20 | 255.255.255.0 |            10.2.2.1 |

## Lab Access Credentials
If you download the `.pkt` simulation file to explore the configurations in Cisco Packet Tracer, you will need these credentials to access the devices:

* **Console Password:** Test@12345
* **Privileged EXEC (Enable):** a1b2c3d4
* **SSH Username:** admin
* **SSH Password:** login@12345

## How to Run It
If you want to test this lab yourself, simply download the `Lab 1 Basic Routing.pkt` file and open it in Cisco Packet Tracer. You can open the command line on any of the PCs to test ping connectivity across the router or use the SSH credentials above to remote into `R1-Core`. Alternatively, you can read the raw configuration files located in this same folder.
