# 🛠️ Active Directory Lab for System Administration

## 📝 Project Description

This project offers a complete lab environment for setting up and managing Active Directory using Windows Server on a virtual machine through Oracle VirtualBox. It serves as an educational resource for IT professionals, system administrators, and students to gain hands-on experience with Windows domain infrastructure and enterprise-grade system administration. The lab guides you through installing Windows Server, configuring it as a Domain Controller with DNS and DHCP, managing users and organizational units (OUs), and integrating a Windows 10 client to simulate a real-world domain environment.

## 🚀 Features

* 🖥️ **Full Windows Server Installation**: Step-by-step guide for installing Windows Server 2019 or later.
* 🛡️ **Domain Controller Setup**: Promote the server to a Domain Controller with Active Directory Domain Services (AD DS).
* 🌐 **DNS and DHCP Configuration**: Configure domain name resolution and IP address assignment.
* 👥 **Active Directory Management**: Create and manage organizational units (OUs), users, groups, and computer objects.
* 📜 **Group Policy Implementation**: Apply Group Policy Objects (GPOs) to manage security, user environments, and system configurations.
* 💻 **Domain-Joined Client Integration**: Join a Windows 10 machine to the domain for simulation of multi-user environments.
* 🧰 **System Administration Practices**:

  * OU design reflecting organizational structure.
  * Delegation of administrative control.
  * GPO management for centralized policy enforcement.
  * Monitoring and managing Active Directory using built-in administrative tools.
  * DNS and DHCP configuration for network services.
  * Routine maintenance and performance monitoring.
  * Backup, restore, and user access auditing.
* ⚙️ **Optional Configurations**:

  * Static IP configuration for consistent network communication.
  * Virtual machine snapshots for rollback and recovery.

## 📦 Prerequisites

Ensure you have the following before setting up:

* 💽 **Oracle VirtualBox**: Installed on your host machine.
* 📀 **Windows Server ISO**: Installation media for Windows Server 2019 or later.
* 💿 **Windows 10 ISO**: For setting up a domain-joined client machine.
* 🧠 **Sufficient System Resources**: Minimum 8 GB RAM and adequate CPU/disk resources.
* 📘 **Basic Networking and Windows Administration Skills**
* 🔐 **Administrative Rights**: To install and configure VirtualBox and virtual networks.

## ⚙️ Installation and Setup Instructions

### 1️⃣ Download and Install Oracle VirtualBox

* Download the latest version from the [Oracle VirtualBox website](https://www.virtualbox.org).
* Install VirtualBox on your host OS following the setup instructions.

### 2️⃣ Create the Windows Server Virtual Machine

* **Create New VM**:

  * Name: `WinServer-AD`
  * Type: Microsoft Windows; Version: Windows Server 2019 or later
  * RAM: Minimum 4 GB (8 GB recommended)
  * Hard Disk: Minimum 40 GB
* **VM Settings**:

  * Set boot order to boot from ISO
  * Configure networking (Bridged or NAT)
  * Assign a static IP address (recommended)

### 3️⃣ Install Windows Server

* Attach the ISO file in the VM's storage settings.
* Boot and install Windows Server with standard configurations.
* Configure networking if needed.

### 4️⃣ Promote Server to Domain Controller

* Launch **Server Manager**
* Install **Active Directory Domain Services (AD DS)**
* After installation, choose **Promote this server to a domain controller**

  * Add a new forest (e.g., `example.local` or `Kernel-Freak.local`)
  * Configure DNS, set DSRM password, and complete the promotion
  * Restart after promotion

### 5️⃣ Configure DNS and DHCP Services

* **🧭 DNS Configuration**:

  * Open **DNS Manager** from Server Manager > Tools.
  * Ensure Forward Lookup Zones and Reverse Lookup Zones are properly configured for your domain.
  * Verify DNS records (A, PTR, SRV) are auto-created and resolvable.
  * Add static records as needed for critical services or client machines.

* **📡 DHCP Configuration**:

  * Open **DHCP Manager** from Server Manager > Tools.
  * Add DHCP role if not already installed.
  * Create a new IPv4 scope with a valid IP address range, subnet mask, and lease duration.
  * Set scope options: router (default gateway), DNS servers (point to domain controller), and domain name.
  * Authorize the DHCP server and activate the scope.

### 6️⃣ Configure Active Directory and System Administration Elements

* Open **Active Directory Users and Computers**
* Create Organizational Units (OUs) to reflect departments (e.g., HR, IT, Finance)
* Create user accounts and assign to OUs
* Create and link GPOs:

  * Set password policies
  * Restrict access to Control Panel
  * Deploy software or scripts
  * Configure login banners, screensavers, and mapped drives
* Use **Group Policy Management Console (GPMC)** for advanced policy settings and linking

### 7️⃣ Set Up and Join a Windows 10 Client

* Create another VM with Windows 10 installed
* Configure networking so it can communicate with the Domain Controller
* Join the client machine to the domain:

  * Go to **System > About > Rename this PC > Change settings**
  * Select Domain and enter domain name (e.g., `Kernel-Freak.local`)
  * Provide administrator credentials when prompted
  * Restart to complete domain join

### 8️⃣ Monitoring, Maintenance, and Administrative Procedures

* **📊 System Logs and Performance Metrics**:

  * Use **Event Viewer** to monitor logs for DNS, DHCP, and Directory Services.
  * Track logon attempts, policy application events, and system errors.
  * Use **Task Manager**, **Performance Monitor**, and **Resource Monitor** for resource tracking.

* **🛠️ Routine Maintenance**:

  * Review event logs regularly.
  * Verify replication health using `repadmin /replsummary`.
  * Clear stale DNS records and ensure DHCP leases are efficiently managed.

* **💾 Backup and Restore**:

  * Use **Windows Server Backup** to schedule regular system state and full backups.
  * Back up the system state, including AD DS, DNS, and DHCP configurations.
  * Test restoration using **Directory Services Restore Mode (DSRM)**.

* **🔍 User Access Auditing**:

  * Enable **Advanced Auditing Policies** via GPO.
  * Track file access, logon events, and privilege use under **Security Logs**.
  * Export and archive logs for long-term auditing.

## 🖼️ Screenshots

\*You will get all the screenshots from the above folder. \*

* VirtualBox VM Configuration
* Windows Server Installation
* Active Directory Domain Controller Promotion
* OU and GPO Setup
* Windows 10 Domain Join Confirmation
* DNS and DHCP Console Views
* Event Viewer and Backup Configurations

## 💡 Usage

This lab environment is ideal for:

* Practicing enterprise-level system administration tasks
* Learning Active Directory, DNS, DHCP, and GPO management
* Simulating real-world IT infrastructure for educational purposes
* Testing configuration changes and policies in a safe environment

## ⚠️ Known Issues

* **Performance Constraints**: Ensure adequate RAM and CPU to run multiple VMs
* **Network Configuration**: May require VirtualBox networking adjustments (Bridged/NAT)
* **Driver Compatibility**: Some drivers may need manual installation for optimal performance

## 🤝 Contributing

Contributions are welcome:

1. Fork this repository
2. Create a feature or fix branch
3. Submit a pull request with a detailed description
4. Open issues for feature discussions or questions

## 📇 Contact / Author Info

* **Samrat Mandal**
* 📧 [samratmandal423@gmail.com](mailto:samratmandal423@gmail.com)
* 🌐 [GitHub](https://github.com/Kernel-Freak) | [LinkedIn](https://www.linkedin.com/in/samrat7/)

For queries  feel free to get in touch!
