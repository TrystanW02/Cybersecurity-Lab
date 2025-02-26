# Computer Specs 💻

*   _CPU_: Intel(R) Core(TM) i7-9750H CPU @ 2.60GHz   2.59 GHz
*   _RAM_: 16.0 GB (15.9 GB usable)
*   _GPU_: NVIDIA GeForce GTX 1660 Ti

---

# Downloads

## *Hypervisor*
* VirtualBox _7.1.6_

## *ISO Images*
* Kali Linux 2024
* Windows Server 2025
* Windows 11 Enterprise
* Ubuntu Live Server _22.04.5_
* Ubuntu Desktop _22.04.5_
* SecurityOnion _2.4.110_

[Find all of these in the downloads folder! 📁](https://github.com/TrystanW02/portfolio-cybersecuritylab/tree/main/downloads)

---

# Provision A New NAT Network In VirtualBox

1.  File >> Tools >> Network Manager
2.  Click “NAT Networks”, then click “Create”
3.  Name  “project-x-network”

# Provision A Virtual Machine

1. Navigate to the *"Machine"* tab, select **New**

![Virtual Box "Machine" Tab](https://github.com/TrystanW02/portfolio-cybersecuritylab/blob/main/images/VirtualBox_Machine_Tab.png)

2. Enter a name for the virtual machine. Keep the folder the same. Select **"Type"** (*this changes throughout the project based on the ISO image used*). Select **"Version"** (*this changes throughout the project based on the ISO image used*).

![Virtual Machine Creation](https://github.com/TrystanW02/portfolio-cybersecuritylab/blob/main/images/Virtual_Machine_Creation.png?raw=true)

3. Add hardware specifications. 4 GBs of RAM (4096 mb) AND 2 CPU processors for each machine, unless explicitly expressed.
   - *For Windows images, click the box to "Enable EFI"*

![Virtual Machine Creation](https://github.com/TrystanW02/portfolio-cybersecuritylab/blob/main/images/Hardware_Specs.png?raw=true)
