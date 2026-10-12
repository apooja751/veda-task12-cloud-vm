# Task 12 — Create and Configure a Cloud Virtual Machine ☁️

## 📌 Project Overview

This project demonstrates how to create and configure a cloud-based virtual machine using **Amazon Web Services (AWS) EC2**. It covers operating system selection, compute resources, storage configuration, network security, and SSH connectivity verification.

## 🎯 Objectives

- Launch a cloud virtual machine using Amazon EC2.
- Configure the operating system, instance type, and storage.
- Configure networking and restrict SSH access.
- Connect to the VM using SSH.
- Verify the operating system and system resources.
- Document the deployment and cleanup process.

## 🛠️ Technologies and Services

- **Cloud Provider:** Amazon Web Services (AWS)
- **Service:** Amazon EC2
- **Operating System:** Ubuntu Server 26.04 LTS
- **Instance Type:** `t3.micro`
- **Storage:** Amazon EBS (`gp3`)
- **Remote Access:** SSH
- **Client:** Windows PowerShell

## ⚙️ Virtual Machine Configuration

|      Parameter     |               Configuration                   |
|--------------------|-----------------------------------------------|
| Instance Name      | `veda-task12-cloud-vm`                        |
| Region             | Asia Pacific (Mumbai) — `ap-south-1`          |
| Operating System   | Ubuntu Server 26.04 LTS                       |
| Architecture       | 64-bit x86                                    |
| Instance Type      | `t3.micro`                                    |
| vCPUs              | 2                                             |
| Memory             | 1 GiB                                         |
| Root Volume        | 8 GiB                                         |
| Volume Type        | General Purpose SSD (`gp3`)                   |
| IOPS               | 3,000                                         |
| Storage Encryption | Enabled                                       |
| SSH Port           | TCP 22                                        |
| SSH Access         | Restricted to a specific IPv4 address (`/32`) |

## 🚀 Implementation Steps

1. Open the AWS Management Console and navigate to Amazon EC2.
2. Select Ubuntu Server 26.04 LTS as the operating system.
3. Configure the instance name and select the `t3.micro` instance type.
4. Configure an 8 GiB encrypted `gp3` root volume.
5. Configure the security group to allow SSH access only from the administrator's IP address.
6. Launch the EC2 instance and verify its status.
7. Connect to the instance from Windows PowerShell using SSH.
8. Run Linux commands to verify the operating system, CPU, memory, hostname, and filesystem.

## 🔐 Security Configuration

A dedicated security group named `veda-task12-vm-sg` was configured.

- SSH access uses TCP port `22`.
- The inbound SSH rule is restricted to a single IPv4 address using a `/32` CIDR range.
- The root EBS volume is encrypted using the default AWS-managed EBS KMS key.
- No HTTP or HTTPS inbound rules were added because they were not required for this task.
- The EC2 private key must be stored securely and must never be uploaded to GitHub.

**Security note:** If the administrator's public IP address changes, update the SSH inbound rule before reconnecting.

## 🧪 Verification Commands

The following commands were executed through the SSH connection to verify the VM configuration.

```bash
# Check the hostname
hostname

# Check filesystem capacity and usage
df -h

# Check Ubuntu version
lsb_release -a

# Check CPU information
lscpu

# Check memory information
free -h
```

The SSH connection was successful, Ubuntu Server was identified, and the system information commands were used to verify the environment.

## 📸 Screenshots and Evidence

The `Screenshorts` folder is intended to contain screenshots documenting the configuration and verification process.

Recommended evidence:

1. `Task12_01_Instance_Configuration.png` — Ubuntu image and instance type.
2. `Task12_02_Network_Security.png` — security group and restricted SSH rule.
3. `Task12_03_Storage_Configuration.png` — EBS root volume configuration.
4. `Task12_04_Instance_Running.png` — running EC2 instance and status checks.
5. `Task12_05_SSH_Connection.png` — successful SSH connection.
6. `Task12_06_System_Information.png` — Ubuntu, CPU, memory, and filesystem verification.

Upload only screenshots that you have actually captured. Rename `Screenshorts` to `screenshots` if you want a correctly spelled, consistent folder name.

## ✅ Result

A cloud virtual machine was successfully created using Amazon EC2. The Ubuntu operating system, compute configuration, encrypted storage, network security rules, SSH connectivity, and system information were configured or verified.

