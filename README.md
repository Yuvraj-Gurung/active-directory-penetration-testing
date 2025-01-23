# Active Directory Penetration Testing

## Project Overview
This documentation provides a step-by-step guide to setting up an Active Directory (AD) lab environment using virtualization software. This lab will help gain hands-on experience with AD concepts, including user and group management, Group Policy Objects (GPOs), and network configuration.

## Prerequisites
- **Virtualization Software**: Oracle VirtualBox
- **ISO Files**: Windows Server 2019 and client Operating system (e.g. Windows 10 Enterprise)
- **Hardware Requirements**: Sufficient CPU, RAM, and disk space to run multiple VMs
- **Network Configuration**: Basic understanding of networking concepts

## Lab Set Up
### I. Setting Up the Virtual Environment
1. **Install Virtualization Software**:
   - Download and install Oracle VirtualBox from their respective websites.
   - Follow the installation instructions provided by the software vendor.

2. **Download ISO Files**:
   - Obtain the ISO files for Windows Server 2019 and Windows 10 Enterprise from the Microsoft website or a trusted source.

### II. Creating Virtual Machines (VMs)
#### Domain Controller (DC)
1. **Create a New VM**:
   - Open the virtualization software and create a new VM.
   - Select the Windows Server 2019 ISO file as the installation source.

*Ref 1: Windows Server Installation 1*
![windows server installation](images/image1.png)

2. **Configure VM Settings**:
   - Allocate sufficient resources (CPU, RAM, and disk space) for the VM.

3. **Install Windows Server**:
   - Follow the installation process to set up Windows Server on the VM.

*Ref 2: Windows Server Installation 2*
![windows server installation](images/image2.png)

*Ref 3: Windows Server Installation 3*
![windows server installation](images/image3.png)

*Ref 4: Windows Server Installation*
![windows server installation](images/image4.png)

*Ref 5: Windows Server Installation*
![windows server installation](images/image5.png)

*Ref 6: Windows Server Installation*
![windows server installation](images/image6.png)

*Ref 7: Windows Server Installation*
![windows server installation](images/image7.png)

*Ref 8: Windows Server Installation*
![windows server installation](images/image8.png)

#### Client Machines
1. **Create Client VMs**:
   - Repeat the process to create additional VMs for client machines using the Windows 10 Enterprise ISO file.

### III. Installing and Configuring Active Directory
#### Install Active Directory Domain Services (AD DS)
1. **Open Server Manager**:
   - On the Domain Controller VM, open Server Manager and select “Add roles and features".

2. **Add AD DS Role**:
   - Follow the wizard to install the Active Directory Domain Services role.

3. **Promote Server to Domain Controller**:
   - After the installation, use the “Promote this server to a domain controller” option.
   - Create a new forest and domain (e.g., ad.lab).

#### Configure DNS
1. **Install DNS Role**:
   - During the AD DS installation, ensure the DNS role is also installed.

2. **Configure DNS Settings**:
   - Verify that the DNS server is correctly configured to handle domain name resolution for the lab network.

#### Create Organizational Units (OUs)
1. **Open Active Directory Users and Computers**:
   - Use the AD management tools to create OUs for organizing users, groups, and computers.

2. **Create OUs**:
   - Create OUs based on your lab requirements (e.g., HR, IT, Sales).

#### Making AD lab Vulnerable
- Open PowerShell as administrator and execute the following commands in powershell.


#### Set Up Group Policy Objects (GPOs)
1. **Open Group Policy Management**:
   - Use the Group Policy Management Console to create and manage GPOs.

2. **Create and Link GPOs**:
   - Create GPOs to enforce security policies and link them to the appropriate OUs.

### IV. Joining Client Machines to the Domain
1. **Network Configuration**:
   - Ensure all VMs are on the same virtual network.

2. **Join Client Machines to the Domain**:
   - On each client machine, open System Properties and use the “Change settings” option to join the domain (e.g., ad.lab).
