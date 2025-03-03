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


## Network Configuration
The following diagram illustrates the network setup of the lab:


![Image](https://github.com/user-attachments/assets/8e4a80f4-d8a8-45d8-8fe8-b26ee8fa4db4)

### **Key Network Components:**
- **Domain Controller (DC - Server 2019)**
  - **NIC (Internet):** Obtains IP from home router via DHCP.
  - **NIC (Internal):** Manually assigned IP **172.16.0.1**.
  - Runs **Active Directory (AD DS)** and acts as a **DHCP server**.
  - This is going to house Active Directory. We're going to give this virtual machine two network adapters. One is going to be used to connect to the outside internet, and the other one is going to be used to connect to     the VirtualBox kind of private network that the clients are going to connect to.

- **Client1 (Windows 10)**
  - Connected to **internal network**.
  - Receives IP from **DHCP Server (DC - 172.16.0.1)**.

- **DHCP Configuration**
  - **Scope:** 172.16.0.100 - 172.16.0.200
  - **Gateway:** 172.16.0.1 (Domain Controller)
  - **DNS:** 127.0.0.1 (Localhost for DC)

- **PowerShell Automation:**
  - Bulk creation of **1,000+ Active Directory users**.

## Lab Setup
### 1. **Installing Virtual Machines**
- Downloaded and installed **VirtualBox** and its extension pack.
- Downloaded **Windows Server 2019 ISO** and **Windows 10 ISO**.
- Created two virtual machines: 
  - **Domain Controller (DC)** running Windows Server 2019
  - **Client1** running Windows 10



### 2. **Configuring the Domain Controller (DC)**
- Installed **Windows Server 2019** on the DC VM.
- Assigned **two network adapters**:
  - **One** for internet connectivity (NAT mode).
  - **One** for internal VirtualBox network (manual IP configuration).
![Image](https://github.com/user-attachments/assets/c97a22c5-7c02-43e4-946a-eebc213240ae)
    
- Set up **Static IP Addressing** for the internal NIC.

![Image](https://github.com/user-attachments/assets/37b64be0-df23-457a-b977-cbe9f5206ba0)
- Installed **Active Directory Domain Services (ADDS)**.

![Image](https://github.com/user-attachments/assets/2c1d1912-f831-4775-990d-c2f16a78d2b4)
- Created a **new domain** (`mydomain.com`).
- Configured **NAT & Routing** to allow client access to the internet.
- Installed and configured **DHCP Server** to provide automatic IP addresses to clients.
 ![Image](https://github.com/user-attachments/assets/ac4fcd26-c31a-49ff-b80b-0765687d9f1a)
 the dhcp server is running
 ![Image](https://github.com/user-attachments/assets/dccf729b-2859-42cc-b311-b2156bb1989e)
 
 ![Image](https://github.com/user-attachments/assets/e49f1288-126b-4393-8bf7-da1721767987)



 ![Image](https://github.com/user-attachments/assets/c111ed9e-131a-4ae9-b379-d5881a29ae41)

### 3. **Automated User Creation using PowerShell**
- Used a **PowerShell script** to bulk create **1000 Active Directory users**.
- Each user was assigned a default password (`Password1`).
- Created an **organizational unit (OU)** to store users.
- The PowerShell script pulled names from a text file and automated account creation.


![Image](https://github.com/user-attachments/assets/05f7d312-1799-4156-bacc-4bc1aadf34f3)
![Image](https://github.com/user-attachments/assets/5dd591ae-28fe-495b-a2c7-0648cb322652)

### 4. **Setting Up Windows 10 Client Machine**
- Installed **Windows 10** on the Client VM.
- Connected the **Client1 VM** to the internal VirtualBox network.
- Verified DHCP was assigning IP addresses correctly.
- Joined the **client machine to the domain (`mydomain.com`)**.
- Logged in using a domain user account created from the PowerShell script.

 ![Image](https://github.com/user-attachments/assets/8095abf5-819b-4bfb-b935-241a67090a55)

![Image](https://github.com/user-attachments/assets/eeb9bb64-ac60-40b1-827e-a83d790bb24e)

![Image](https://github.com/user-attachments/assets/adce530b-6c3e-4c42-b7ff-cd83a054043c)

![Image](https://github.com/user-attachments/assets/b0ea8fdf-9ee8-464e-9df8-55a710ed7d5b)

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



---
Feel free to fork, modify, or expand upon this project!

