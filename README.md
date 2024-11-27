![image](https://github.com/user-attachments/assets/fb2fae59-e275-4385-a3a6-be222b2e24c3)
# Setting Up a Domain Controller in Azure

## Overview
This project demonstrates the step-by-step process of setting up a domain controller (DC) and client machine in Microsoft Azure. The lab covers creating resources, configuring networking, and ensuring proper communication between the domain controller and client.

---

## Environments and Technologies Used
- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Windows Active Directory Domain Services

## Operating Systems Used
- Windows Server 2022
- Windows 10

## List of Prerequisites
- An active Microsoft Azure subscription
- Basic knowledge of Remote Desktop Protocol (RDP)
- Familiarity with virtual networking in Azure
- Windows Server administration skills
- The ability to set static IPs and DNS settings in Azure

---

## Step 1: Setting Up the Domain Controller (DC-1)

### Tasks Performed:
1. **Create a Resource Group:** 
   - Established a resource group to organize all related resources.
     ![image](https://github.com/user-attachments/assets/c562ac84-4767-40fe-a284-beca7238c436)

2. **Set Up a Virtual Network and Subnet:**
   - Configured networking to allow communication between the DC and other machines.
     ![image](https://github.com/user-attachments/assets/74de5d03-214d-4d46-974e-fa3f14ba6eaa)

3. **Create the Domain Controller VM:**
   - **Operating System:** Windows Server 2022  
   - **VM Name:** `DC-1`  
   - **Credentials:**
     - Username: `labuser`
     - Password: `Cyberlab123!`
   - Configured the NIC private IP address to be static for consistency.
     ![image](https://github.com/user-attachments/assets/35f7fa83-e0b2-4948-b758-ce5a0f9cdc2e)

4. **Disable Windows Firewall:**
   - Temporarily disabled the firewall to test connectivity.
     ![image](https://github.com/user-attachments/assets/b635b9bd-2478-4b59-96f3-da79372307ca)

---

## Step 2: Setting Up the Client Machine (Client-1)

### Tasks Performed:
1. **Create the Client VM:**
   - **Operating System:** Windows 10  
   - **VM Name:** `Client-1`  
   - **Credentials:**
     - Username: `labuser`
     - Password: `Cyberlab123!`
   - Connected to the same region and Virtual Network as `DC-1`.
     
2. **Configure DNS Settings:**
   - Updated Client-1's DNS settings to point to `DC-1’s Private IP`.
     ![image](https://github.com/user-attachments/assets/d9f316af-8473-45aa-a0d3-c0f4f8ff67c6)

   - Restarted Client-1 to apply changes.
3. **Test Connectivity:**
   - Verified the client could ping the DC-1 private IP address successfully.
     ![image](https://github.com/user-attachments/assets/62811970-db13-4de1-8c2d-8d1634f4d5a3)

   - Ensured DNS settings were correctly updated by running `ipconfig /all`.
     ![image](https://github.com/user-attachments/assets/21217b47-da6b-4e0a-ad2e-02b80dff0217)

---

## Final Steps

1. **VM Preservation:**
   - The VMs were left intact for use in future labs. For cost-saving purposes, the VMs were stopped within the Azure portal when not in use.
2. **Future Scope:**
   - This setup lays the groundwork for additional Active Directory-related tasks, such as user management and group policies.
