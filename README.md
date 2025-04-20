# Active-Directory

## Project Description

This project provides a comprehensive lab environment for setting up and configuring Active Directory on a Windows Server virtual machine using Oracle VirtualBox. It is an educational resource designed for IT professionals, students, and system administrators to practice and test Windows domain management in a controlled, non-production environment. The setup includes installing Windows Server, promoting it to a Domain Controller, configuring DNS, creating user accounts and organizational units (OUs), and adding a second Windows machine as a domain-joined client for testing.

## Features

- **Full Windows Server Installation**: Step-by-step guide for installing Windows Server 2019 (or later).
- **Domain Controller Promotion**: Procedures to promote the server to a Domain Controller.
- **DNS Configuration**: Detailed instructions for setting up and managing DNS.
- **Active Directory Management**: Creation of organizational units (OUs) and user accounts.
- **Domain-Joined Client Setup**: Instructions for joining a second Windows machine to the domain.
- **Optional Configurations**:
  - Static IP address configuration.
  - Taking snapshots for quick recovery.
  - Testing with domain-joined client machines.

## Prerequisites

Before you begin, ensure you have the following:

- **Oracle VirtualBox**: Installed on your host machine.
- **Windows Server ISO**: Windows Server 2019 (or later) installation media.
- **Second Windows Machine ISO**: For setting up a domain-joined client (optional).
- **Sufficient System Resources**: Adequate RAM, CPU, and disk space for running multiple virtual machines.
- **Basic Knowledge**: Familiarity with Windows Server administration and network configuration.
- **Administrative Rights**: Permissions to install VirtualBox and configure virtual network settings on your host machine.

## Installation and Setup Instructions

Follow these detailed steps to set up the lab environment:

### 1. Download and Install Oracle VirtualBox

- Visit the [Oracle VirtualBox website](https://www.virtualbox.org) and download the latest version.
- Install VirtualBox following the on-screen instructions for your host operating system.

### 2. Create the Windows Server Virtual Machine

- **New VM Setup**:
  - Open VirtualBox and click on **New**.
  - Name the VM (e.g., `WinServer-AD`), set the Type to "Microsoft Windows", and choose the appropriate Version (Windows Server 2019 or later).
  - Allocate at least 4 GB of RAM (more for improved performance).
  - Create a virtual hard disk (minimum 40 GB recommended).

- **Virtual Machine Configuration**:
  - Open the **Settings** for the VM.
  - Under **System > Motherboard**, set the boot order to prioritize the optical drive for ISO booting.
  - Configure network settings in **Network**: Choose "Bridged" or "NAT" based on your testing requirements. Set up a static IP if needed for better management.

### 3. Install Windows Server

- Attach the Windows Server installation ISO in the **Storage** section.
- Start the VM and follow the installation prompts:
  - Select language, time, and keyboard preferences.
  - Proceed with the installation and complete the initial configuration.
  - If configuring a static IP, do this during installation or later via network settings.

### 4. Promote the Windows Server to a Domain Controller

- **Configure Active Directory**:
  - Once Windows Server is installed, open **Server Manager**.
  - Click on **Add roles and features**.
  - Select **Active Directory Domain Services** and follow the wizard to install the necessary roles and features.

- **Domain Controller Promotion**:
  - When installation completes, click the notification flag in Server Manager and choose **Promote this server to a domain controller**.
  - Select **Add a new forest** and enter a root domain name (e.g., `example.local`).
  - Configure the DNS options, choose your domain functional levels, and set a Directory Services Restore Mode (DSRM) password.
  - Complete the promotion wizard and allow the machine to restart.

### 5. Configure DNS, Create OUs, and User Accounts

- After reboot, launch **Server Manager** again.
- Open **Active Directory Users and Computers**:
  - Create organizational units (OUs) to structure your directory.
  - Set up user accounts, security groups, and apply relevant policies.

### 6. Set Up the Domain-Joined Client Machine

- **Create a New VM for the Client**:
  - Follow similar steps as for the Windows Server VM to create a client machine.
  - Use a Windows client operating system (Windows 10 or later recommended).

- **Join the Client to the Domain**:
  - Boot the client VM and configure its network settings, ensuring it can reach the domain controller.
  - In the client system settings, navigate to **System > About > Rename this PC (advanced)** and select **Change settings**.
  - Choose **Domain**, enter the domain name (e.g., `example.local`), in my case i have used `Kernel-Freak.local` and provide administrator credentials when prompted.
  - Restart the client machine to complete the domain join process.

## Screenshots

Below are placeholder screenshots. Replace these with your own screenshots from the setup process:

- Oracle VirtualBox VM Configuration
- Windows Server Installation
- Active Directory Promotion Wizard
- Domain-Joined Client Configuration

## Usage

This lab environment is intended for educational and testing purposes. Use it to:

- Learn and experiment with Active Directory setup and management.
- Practice configuring DNS and domain policies.
- Test domain-joined client scenarios and network configurations.
- Simulate common enterprise network scenarios for troubleshooting and educational exercises.

## Known Issues

- **Resource Limitations**: Ensure your host machine has enough resources if running multiple VMs simultaneously.
- **Network Configuration Challenges**: Depending on your network setup, additional VirtualBox network adjustments might be needed, especially with NAT or bridged modes.
- **Driver Compatibility**: Windows Server and client VMs might require additional drivers for optimal performance in VirtualBox. Consult VirtualBox documentation if issues arise.

## Contributing

Contributions are welcome! If you have suggestions or improvements:

1. Fork the repository.
2. Create a new branch for your feature or bug fix.
3. Submit a pull request with a detailed explanation of your changes.
4. For major changes, consider opening an issue first for discussion.


## Contact / Author Info

- **Author**: Samrat Mandal
- **Email**: samratmandal423@gmail.com
- **GitHub**: https://github.com/Kernel-Freak

For additional questions or further discussion, please feel free to contact the author.
