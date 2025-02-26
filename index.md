# Project Overview :briefcase:
> This project was based on Grant Colin's Cybersecurity Homelab pproject that can be found [here](https://projectsecurity.teachable.com/)!

## Computer Specs :computer:

*   _CPU_: Intel(R) Core(TM) i7-9750H CPU @ 2.60GHz   2.59 GHz
*   _RAM_: 16.0 GB (15.9 GB usable)
*   _GPU_: NVIDIA GeForce GTX 1660 Ti

## Downloads :arrow_down:

### *Hypervisor*
* VirtualBox _7.1.6_

### *ISO Images*
* Kali Linux 2024
* Windows Server 2025
* Windows 11 Enterprise
* Ubuntu Live Server _22.04.5_
* Ubuntu Desktop _22.04.5_
* SecurityOnion _2.4.110_

[Find all of these in the downloads folder! 📁](https://github.com/TrystanW02/portfolio-cybersecuritylab/tree/main/downloads)

## NAT Network :signal_strength:

* **Name:** lab-network
* **IP Address Range:** 10.0.0.0/24
  - **Usable Range:** 10.0.0.1 - 10.0.0.254
  - **DHCP Dynamic Scope:** 10.0.0.100 - 10.0.0.200 

## Host :busts_in_silhouette:

| **Hostname [lab-...]** | **IP Address**          | **Function**                       |
|------------------------|-------------------------|------------------------------------|
| dc (corp.lab-dc.com)   | 10.0.0.5                | Domain Controller (DNS, DHCP, SSO) |
| email-svr              | 10.0.0.8                | SMTP Relay Server                  |
| sec-box                | 10.0.0.10               | Dedicated Security Server          |
| sec-work               | 10.0.0.103 or (dynamic) | Security Playground                |
| win-client             | 10.0.0.100 or (dynamic) | Windows Workstation                |
| linux-client           | 10.0.0.101 or (dynamic) | Linux Desktop Workstation          |
| attacker               | dynamic                 | Attacker Environment               |

## Accounts & Passwords :page_with_curl:

| **Account**             | **Password**     | **Host**         |
|-------------------------|------------------|------------------|
| Administrator           | @boomersooner25! | ...-dc           |
| johnd@corp.lab-dc.com   | @password123!    | ...-win-client   |
| janed@linux-client      | @password123!    | ...-linux-client |
| lab-sec-work            | @password123!    | ...-sec-work     |
| sec-work@sec-box        | @password123!    | ...-sec-box      |
| email-svr@lab-email-svr | @password123!    | ...-email-svr    |
| attacker@attacker       | attacker         | attacker         |

## VirtualBox VMs :robot:

| **VM Name**        | **Operating System**  | **Specs**       | Storage (Minimum) |
|--------------------|-----------------------|-----------------|-------------------|
| [lab-dc]           | Windows Server 2025   | 2 CPU / 4096 MB |50 GBs             |
| [lab-win-client]   | Windows 11 Enterprise | 2 CPU / 4096 MB |80 GBs             |
| [lab-linux-client] | Ubuntu 22.04 Desktop  | 1 CPU / 2048 MB |80 GBs             |
| [lab-sec-work]     | Security Onion        | 1 CPU / 2048 MB |55 GBs             |
| [lab-sec-box]      | Ubuntu 22.04 Desktop  | 2 CPU / 4096 MB |80 GBs             |
| [lab-email-svr]    | Ubuntu Server 22.04   | 1 CPU / 2048 MB |25 GBs             |
| [attacker]         | Kali Linux 2024       | 1 CPU / 2048 MB |55 GBs             |

## Tools :toolbox:

### *Enterprise Tools + Defense*

* **Microsoft Active Directory:** A centralized directory service that manages users, devices, and permissions in a Windows domain environment
* **Wazuh:** An open-source security platform for threat detection, incident response, and compliance monitoring
* **Postfix:** A mail transfer agent (MTA) used to route and deliver email securely in Unix-based systems

### Offense

* **Evil-WinRM:** A post-exploitation tool that allows remote command execution on Windows systems using WinRM
* **Hydra:** A fast and flexible password-cracking tool that supports numerous authentication protocols
* **SecLists:** A comprehensive collection of security-related wordlists used for reconnaissance, brute-force attacks, and pentesting
* **NetExec:** A remote command execution tool for managing Windows machines across a network
* **XFreeRDP:** An open-source implementation of the Remote Desktop Protocol (RDP) for accessing Windows systems remotely

---

# Provisioning Technologies :electric_plug:

## Provision A New NAT Network In VirtualBox

### *1.  Navigate to the *"File"* tab, select *"Tools"* then click *"Network Manager"**

![Network Manager](https://github.com/TrystanW02/portfolio-cybersecuritylab/blob/main/images/network_provision/Network_Manager.png?raw=true)

### *2.  Click *“NAT Networks”*, then click *“Create”**

![Network Manager](https://github.com/TrystanW02/portfolio-cybersecuritylab/blob/main/images/network_provision/Create_NATNetwork.png?raw=true)

### 3.  *Name the network and choose an IPv4 prefix. Refer to the **"Project Overview"** section for IPv4 prefixes.*

![Network Manager](https://github.com/TrystanW02/portfolio-cybersecuritylab/blob/main/images/network_provision/Naming_Network.png?raw=true)

## Provision A Virtual Machine

### *1. Navigate to the *"Machine"* tab, select *New**

![Virtual Box "Machine" Tab](https://github.com/TrystanW02/portfolio-cybersecuritylab/blob/main/images/VirtualBox_Machine_Tab.png)

### *2. Enter a name for the virtual machine. Keep the folder the same. Select **"Type"** (*this changes throughout the project based on the ISO image used*). Select **"Version"** (*this changes throughout the project based on the ISO image used*).*

![Virtual Machine Creation](https://github.com/TrystanW02/portfolio-cybersecuritylab/blob/main/images/Virtual_Machine_Creation.png?raw=true)

### *3. Add hardware specifications. 4 GBs of RAM (4096 mb) AND 2 CPU processors for each machine, unless explicitly expressed.*
   - *For Windows images, click the box to "Enable EFI"*

![Virtual Machine Creation](https://github.com/TrystanW02/portfolio-cybersecuritylab/blob/main/images/Hardware_Specs.png?raw=true)

### *4. Add hard disk specifications. Minimum 50 GB of space.*

![Virtual Machine Creation](https://github.com/TrystanW02/portfolio-cybersecuritylab/blob/main/images/Hard_Disk_Specs.png?raw=true)

### *5. Right click the new machine, click *"Settings"**

![Virtual Machine Configuration](https://github.com/TrystanW02/portfolio-cybersecuritylab/blob/main/images/LabWinClient_Settings.png?raw=true)

### *6. Select the *"Storage"* tab, click the *"Empty"* storage device, then select *"Choose a disk file".**

![Virtual Machine Configuration](https://github.com/TrystanW02/portfolio-cybersecuritylab/blob/main/images/LabWinClient_Storage_Settings.png?raw=true)

### *7. Navigate to the ISO image location and select the appropriate ISO image*
