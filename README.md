# networkwalks-
networkwalks-B083-week1-Cybersecurity-lab-setup
Cybersecurity Lab Setup

Project Overview
This project focuses on setting up a virtual cybersecurity and penetration-testing laboratory using VirtualBox and Kali Linux.

The aim of the lab is to create a controlled environment where cybersecurity tools, network scanning, reconnaissance, vulnerability assessment, and other security-testing activities can be performed safely and repeatedly. The lab is configured on a private virtual network so that additional machines can be added later and used as targets for authorized security testing.

Objectives
The main objectives of this project are to:

Install and configure VirtualBox.
Install/import Kali Linux as a virtual machine.
Create a private NAT Network for the cybersecurity lab.
Configure network connectivity for Kali Linux.
Assign a consistent IP address to the Kali VM.
Verify network connectivity and DNS resolution.
Take a clean VM snapshot for recovery.
Document the complete setup process.
Prepare the environment for future cybersecurity projects.
Purpose of the Lab
The lab supported an isolated and controlled environment for cybersecurity learning and authorized security testing. Also can be used for activities such as:

Network reconnaissance
Port scanning
Vulnerability assessment
Packet analysis
Web security testing
Exploitation practice
Security-tool experimentation
⚠️ It is important to note that this laboratory must only be used for systems that you own or have proper permission to test. Ensure not to use the lab or its tools to attack unauthorized systems.

Lab Configuration
🧩 Component	⚙️ Configuration
🖥️ Host OS	Windows 11
🧠 Host RAM	8 GB
⚡ Processor	Intel Core i5
🧰 Hypervisor	VirtualBox 7.2
🐉 Security OS	Kali Linux 2026.2
🧠 Kali RAM	2048 MB
🌐 Virtual Network	NAT Network
📡 Network Address	10.0.0.0/24
🐧 Kali IP Address	10.0.0.2/24
🚪 Default Gateway	10.0.0.1
🌍 DNS Server	8.8.8.8
Lab Setup Procedure
Step 1. Install 7-Zip
In order to extract the Kali Linux virtual machine package, 7-zip was installed to extract it, because the package downloaded as a .7z archive. Tool: 7-Zip

Step 2. Install VirtualBox
VirtualBox was installed as the hypervisor.

Step 3. Create the NAT Network
A dedicated NAT Network was created in VirtualBox.

Configuration: Network Name: NatNetwork IPv4 Prefix: 10.0.0.0/24 DHCP: Enabled IPv6: Disabled

NAT Network settings

A NAT Network was selected because multiple virtual machines connected to the same NAT Network can communicate with one another while also having outbound network connectivity.

This network allow future attacker and target VMs to communicate within the lab.

Step 4. Import Kali Linux
The Kali Linux virtual machine was downloaded from the official Kali Linux website and imported into VirtualBox.

The VM network adapter was configured as follows:

Adapter 1 Attached to: NAT Network Network: NatNetwork Adapter Type: Intel PRO/1000 MT Desktop


The VM was allocated:

RAM: 2048 MB
A shared folder was also configured for transferring required files between the host operating system and the Kali VM.

Step 5. Configure the Kali Linux Network
The Kali Linux network configuration was checked and configured with a consistent IPv4 address.

Example configuration:

IP Address: 10.0.0.2 Subnet Mask: 255.255.255.0 Gateway: 10.0.0.1 DNS: 8.8.8.8

A Static IP address makes it easier to document the lab and reference the Kali machine in future exercises.

Editing wired connections

Step 6. Create a Clean VM Snapshot
After the successful configuration, a VirtualBox snapshot was created.

The snapshot name:

New Kali - Network Setup

The snapshot represents the clean baseline of the laboratory.

If a future exercise changes or damages the VM configuration, the machine can be restored to this baseline.

Lab Verification
✅ Test	🧾 Command	🎯 Expected Result
🌐 Check IP address	ip a	Correct Kali IP displayed
📡 Test gateway	ping 10.0.0.1	Successful replies
🌍 Test Internet connectivity	ping 8.8.8.8	Successful replies
🔎 Test DNS resolution	nslookup networkwalks.com	Domain resolves
🧰 Verify Nmap	nmap --version	Nmap version displayed
🔄 Verify snapshot	Restore snapshot and run ip a	Baseline configuration restored
Example Results
IP Address: 10.0.0.2/24

Gateway: 10.0.0.1

DNS: 8.8.8.8

What I Learned
During the course of this project, I learned how to create and configure a virtual environment for cybersecurity practice.

The main concepts I learned include:

1. NAT vs NAT Network
A standard NAT configuration and a NAT Network serve different purposes.

NAT allows a VM to access internet through the host machine, but does not allow direct communication between VMs by default.

NAT Network allows multiple VMs connected to the same network to communicate with each other while also having internet access.

This is useful when building a multi-machine cybersecurity laboratory.

2. Virtual Machine Networking
I learned how VirtualBox virtual network adapters connect virtual machines to different types of networks and how network configuration affects communication between machines.

3. Static IP Configuration
I learned how to configure and verify IPv4 addressing, subnet masks, gateways, and DNS settings in Kali Linux.

4. VM Snapshots
I learned that it is important to create clean snapshot before performing risky or experimental activities.

This provides a known-good recovery point for future cybersecurity exercises.

5. Documentation
I learned that documenting commands, configuration, screenshots, problems, and solutions is an important part of a professional cybersecurity project.

Security & Ethical Use
This laboratory is intended strictly for education purposes only.

Tools & Resources
7-Zip: https://7-zip.org/download.html
VirtualBox: https://virtualbox.org/wiki/Downloads
Kali Linux: https://kali.org/get-kali
👤 Author
Odife Jude
Cybersecurity Professional B083

LinkedIn: https://www.linkedin.com/in/odife-jude-2268b738a?utm_source=share_via&utm_content=profile&utm_medium=member_android

Project Information
<img width="1920" height="1080" alt="Screenshot From 2026-09-23 23-47-38" 
  src="https://github.com/user-attachments/assets/1d1e6483-b99f-44a6-a3a1-3c06713a241d" />
<img width="462" height="359" alt="Screenshot From 2026-09-24 00-56-41" src="https://github.com/user-attachments/assets/687e01a5-3db1-4ed6-90ed-9b087cc01af6" />


Program Name: Cybersecurity at Networkwalks | Week: 01 | Project: Cybersecurity & Pentesting Lab Setup | Repository: GitHub

Acknowledgement
This project's structure and documentation structure was inspired by Waqas Karim CCIE
