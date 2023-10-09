# Network Security Setup with Intrusion Prevention System (IPS)

![Project Image](https://github.com/ma7mouddiaa/pfSense-Snort-Security-Setup/blob/main/unknown_2023.10.05-21.02%20(2).png)

**Building a Secure Network Environment with VMware, pfSense, Snort, and Metasploitable**

In this project, I've meticulously designed and implemented a network security setup utilizing an Intrusion Prevention System (IPS) to enhance the security of our simulated environment. I've employed VMware to simulate the network, with a vulnerable server (Metasploitable) and Kali Linux machine connected to separate networks. pfSense, acting as a powerful network router, plays a pivotal role in enabling communication between these networks, and Snort, a robust Intrusion Detection System (IDS), is configured on an Ubuntu server to monitor and block specific network traffic.

## Table of Contents

- [Introduction](#introduction)
- [Project Architecture](#project-architecture)
- [Setup and Configuration](#setup-and-configuration)
  - [VMware Setup](#vmware-setup)
  - [Network Configuration](#network-configuration)
  - [pfSense Configuration](#pfsense-configuration)
  - [Snort Configuration](#snort-configuration)
- [Testing](#testing)
- [Contributing](#contributing)
- [License](#license)

## Introduction

Cybersecurity is a critical concern in today's digital landscape, and this project aims to create a secure network setup for testing and experimentation. By utilizing various technologies such as VMware, pfSense, Snort, and Metasploitable, I've designed a network that not only facilitates a realistic environment but also enables monitoring and prevention of potential security threats.

## Project Architecture

The project's architecture is carefully crafted to replicate a real-world scenario with segregated networks and comprehensive security measures.

- **Metasploitable (Vulnerable Server):**
  - Virtual machine representing a vulnerable server, intentionally designed to be exploitable, connected to an internal network (`10.0.1.0/24`).

- **Kali Linux Machine:**
  - Virtual machine with Kali Linux, a popular penetration testing toolkit, connected to an external network (`192.168.179.0/24`) via NAT and a separate NIC.

- **pfSense:**
  - Virtual machine acting as a robust router to facilitate secure communication between internal and external networks.

- **Snort on Ubuntu Server:**
  - Intrusion detection and prevention system installed on an Ubuntu server, operating in inline mode.

## Setup and Configuration

Let's delve into the step-by-step setup and configuration process, ensuring a robust and secure network environment.

### VMware Setup

VMware is the foundation of our network simulation, providing the virtualization platform necessary to run and manage our virtual machines.

1. **Download and Install VMware:**
   - Download the appropriate version of VMware based on your operating system.
   - Follow the installation wizard to complete the setup.

2. **Create Virtual Machines:**
   - Launch VMware and create virtual machines for Metasploitable, Kali Linux, pfSense, and Ubuntu server.
   - Configure hardware settings, such as memory, CPU, and network adapters.

### Network Configuration

Configuring the networks is a crucial step to ensure proper communication and isolation between the simulated machines.

1. **Create Internal and External Networks:**
   - Define and set up internal (`10.0.1.0/24`) and external (`192.168.179.0/24`) networks in VMware.
   - Assign the appropriate network adapters to each virtual machine.

### pfSense Configuration

Configuring pfSense as the router is essential to enable seamless communication between internal and external networks.

1. **Install and Configure pfSense:**
   - Download the pfSense ISO and install it on a virtual machine.
   - Follow the installation wizard to configure network interfaces and settings.

### Snort Configuration

Configuring Snort on an Ubuntu server in inline mode enhances the security posture of the network.

1. **Install and Configure Snort:**
   - Install Snort on the Ubuntu server and configure it to operate in inline mode.
   - Set up rules to block access to Facebook and ICMP traffic from external to internal networks.
   - ![Snort-Rules](https://github.com/ma7mouddiaa/pfSense-Snort-Security-Setup/blob/main/2023-10-09-11h43m51s483.png)

## Testing

To ensure the effectiveness of our security setup, thorough testing is necessary.

1. **Access Control Testing:**
   - Test the Facebook access rule to confirm that access is blocked from all networks.
   - ![alret-facebook-traffic](https://github.com/ma7mouddiaa/pfSense-Snort-Security-Setup/blob/main/2023-10-09-11h44m26s971.png)
2. **ICMP Traffic Testing:**
   - Test the ICMP traffic block rule to ensure ICMP packets from the external network to the internal network are blocked.
   - ![pinging-internal-network-alerted](https://github.com/ma7mouddiaa/pfSense-Snort-Security-Setup/blob/main/2023-10-09-11h44m40s521%20(2).png)



## Contributing

Contributions to improve and extend this project are encouraged! If you have suggestions, ideas, or would like to contribute, please reach out https://www.linkedin.com/comm/in/mahmoud-diaa-cybersamurai

## License

This project is licensed under the [MIT License](LICENSE).
