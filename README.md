# Kali Linux VM Lab Set Up

## 📌 Overview

This lab documents the deployment and initial configuration of a Kali Linux virtual machine using VirtualBox.

The goal of this lab was to build a controlled, isolated security testing environment that will be used in future labs. This project focuses strictly on environment setup — no scanning or exploitation was performed at this stage.

### Skills Demonstrated

- Virtual machine provisioning  
- Appliance import using OVA  
- Network configuration (NAT)  
- Basic Linux validation and connectivity testing  
- Technical documentation practices  

---

## Software Used

### VirtualBox

- **Version:** 7.2.6  
- **Extension Pack:** 7.2.6  

Official download source:  
https://www.virtualbox.org/wiki/Downloads

The Extension Pack was installed to enable additional functionality such as improved device support and enhanced VM capabilities.


---

### Kali Linux Virtual Machine

For this lab, I used the official pre-built VirtualBox appliance provided by Kali Linux.

Official download page:  
https://www.kali.org/get-kali/#kali-virtual-machines

The pre-built image includes:

- Preconfigured VirtualBox settings  
- Guest tools installed  
- Default credentials

## Importing the Kali VM

The downloaded `.ova` file was imported using:

**File → Import Appliance**

During import, I reviewed resource allocation settings before finalizing.


---

## Virtual Machine Configuration

After import, the following settings were verified and adjusted as needed:

- **RAM allocation:** 4GB  
- **CPU allocation:** 2 cores  
- **Network mode:** NAT  


### Why NAT?

NAT was selected to:

- Allow internet access for updates  
- Keep the VM isolated from the host’s local network  
- Reduce risk when using security tools in future labs  

This ensures the lab remains contained and controlled.

---

## Post-Deployment Configuration

Once the VM was running:

- Logged into Kali  
- Updated system packages  
- Verified network connectivity  

System update:

```
sudo apt update && sudo apt upgrade -y
```

---

## Network Validation

To confirm proper configuration, I verified:

- IP address assignment
- Default route
- Internet connectivity

Commands used:

```
ip a
ip route
ping google.com
```

The VM successfully obtained a private IP address via NAT and was able to reach external hosts.

---

## Security Considerations

This lab was conducted in an isolated virtual environment for educational purposes only.

- No external scanning was performed
- No unauthorized systems were targeted
- All tools will be used strictly within controlled lab environments

Maintaining proper isolation is essential when working with security-focused operating systems.
