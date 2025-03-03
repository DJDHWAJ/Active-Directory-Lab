# Active Directory Lab using VirtualBox

## Objective
This project focuses on setting up an **Active Directory (AD) lab** on a personal computer using VirtualBox. The goal is to provide hands-on experience with Active Directory, Windows networking, and related infrastructure components. This lab simulates a small corporate network where a domain controller manages client authentication, DHCP, and NAT for internal networking.

## Tools & Technologies Used
- **Oracle VirtualBox** - For running virtual machines.
- **Windows Server 2019** - Used to set up the Domain Controller (DC).
- **Windows 10** - Used as the client machine.
- **PowerShell** - Scripted bulk user creation.
- **DHCP, NAT & Routing** - Configured for network communication.
- **Active Directory Domain Services (ADDS)** - Implemented for user and device authentication.
- **DNS Server** - Configured within the domain controller.
- **VirtualBox Guest Additions** - For better performance and usability.
- **Internet Explorer Configuration** - To download required scripts and configurations.

## Lab Setup
### 1. **Installing Virtual Machines**
- Downloaded and installed **VirtualBox** and its extension pack.
- Downloaded **Windows Server 2019 ISO** and **Windows 10 ISO**.
- Created two virtual machines: 
  - **Domain Controller (DC)** running Windows Server 2019
  - **Client1** running Windows 10

 **Screenshot Placeholder:** _Upload a screenshot of VirtualBox showing both VMs_

### 2. **Configuring the Domain Controller (DC)**
- Installed **Windows Server 2019** on the DC VM.
- Assigned **two network adapters**:
  - **One** for internet connectivity (NAT mode).
  - **One** for internal VirtualBox network (manual IP configuration).
- Set up **Static IP Addressing** for the internal NIC.
- Installed **Active Directory Domain Services (ADDS)**.
- Created a **new domain** (`mydomain.com`).
- Configured **NAT & Routing** to allow client access to the internet.
- Installed and configured **DHCP Server** to provide automatic IP addresses to clients.

 **Screenshot Placeholder:** _Upload a screenshot of the DC network configuration_

### 3. **Automated User Creation using PowerShell**
- Used a **PowerShell script** to bulk create **1000 Active Directory users**.
- Each user was assigned a default password (`Password1`).
- Created an **organizational unit (OU)** to store users.
- The PowerShell script pulled names from a text file and automated account creation.

 **Screenshot Placeholder:** _Upload a screenshot of the PowerShell script in execution_

### 4. **Setting Up Windows 10 Client Machine**
- Installed **Windows 10** on the Client VM.
- Connected the **Client1 VM** to the internal VirtualBox network.
- Verified DHCP was assigning IP addresses correctly.
- Joined the **client machine to the domain (`mydomain.com`)**.
- Logged in using a domain user account created from the PowerShell script.

 **Screenshot Placeholder:** _Upload a screenshot of Client1 successfully joined to the domain_

## Key Steps Followed
### **Step 1: VirtualBox Setup**
1. Installed **VirtualBox** and the **Extension Pack**.
2. Downloaded **Windows Server 2019** and **Windows 10 ISOs**.
3. Created two virtual machines (**DC and Client1**).

### **Step 2: Setting Up the Domain Controller (DC)**
1. Installed **Windows Server 2019**.
2. Assigned **two network interfaces (NAT & Internal Network)**.
3. Configured **IP Addressing**.
4. Installed **Active Directory Domain Services (ADDS)**.
5. Created **mydomain.com**.
6. Configured **DHCP & NAT for internal network connectivity**.

### **Step 3: Automating User Creation**
1. Used **PowerShell script** to create **1000 users**.
2. Set **default passwords**.
3. Verified users in **Active Directory Users and Computers (ADUC)**.

### **Step 4: Setting Up Windows 10 Client**
1. Installed **Windows 10**.
2. Assigned to **internal network**.
3. Verified **DHCP assignment**.
4. Joined the **domain (mydomain.com)**.
5. Logged in using **domain credentials**.

 **Screenshot Placeholder:** _Upload a screenshot of successful user login_

## Achievements
- Successfully **deployed an Active Directory environment**.
- Configured **DNS, DHCP, NAT, and Routing**.
- Automated **user creation** with PowerShell.
- Demonstrated how a domain-joined client can authenticate with AD.
- Simulated a small **corporate IT network setup** for hands-on learning.

## How to Use This Lab
1. **Follow the setup instructions** to build the environment from scratch.
2. Experiment with **Group Policies, User Management, and Network Configurations**.
3. Modify the PowerShell script to create **custom users or additional OUs**.
4. Extend the lab by adding **file servers, remote desktop services, or security policies**.

## Conclusion
This project provides foundational knowledge for managing **Windows Server, Active Directory, and enterprise networking**. It serves as a stepping stone for those pursuing careers in **System Administration, Network Security, or IT Infrastructure Management**.



## Screenshots
 **Upload relevant screenshots to make the documentation more visually informative!**


