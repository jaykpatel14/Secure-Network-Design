# Secure Network Design for eLearning Platforms with Cisco Packet Tracer

This project demonstrates how to create a secure network design for a fictional eLearning company, `LearnSec.local`, using Cisco Packet Tracer. It showcases best practices for designing a secure environment using firewalls, VLANs, and secure configurations.

## Overview

Building a secure network for an eLearning platform is crucial for protecting sensitive student data. This guide demonstrates how to design a secure network using Cisco Packet Tracer, covering:

- **Secure Network Principles**: Defense-in-depth, least privilege, and more.
- **Network Design**: Firewall configuration, VLAN creation, and IP allocation with VLSM.
- **Security Configurations**: Secure setup of network devices.

---

## Secure Network Design Principles

- **Defense in Depth**: Implement firewalls, intrusion detection systems (IDS), network segmentation, and data encryption for comprehensive security.
- **Least Privilege**: Assign access permissions based on job roles, ensuring users only access the necessary systems and data.
- **Segregation of Duties**: Separate network administration tasks to prevent unauthorized access.
- **Economy of Mechanism**: Use standardized protocols and keep configurations simple.
- **Fail-Safe Defaults**: Configure network devices to deny all traffic by default, allowing only authorized traffic.
- **Complete Mediation**: Implement real-time access controls to validate user permissions for every network resource.
- **Open Design**: Rely on well-established security protocols and best practices for a transparent and secure network architecture.

---

## Network Design in Cisco Packet Tracer

![image](https://github.com/user-attachments/assets/e85b249d-2555-4c08-bc69-60cfc9fd872f)


The network design consists of various components connected for efficient management and security:

- **Router**: Connects LearnSec.local’s network to the internet.
- ![image](https://github.com/user-attachments/assets/5729c161-1eb8-49bc-a97e-46a7e82bc1a6)

- **Firewall**: Provides internal network security; pfSense firewall is used for ease of configuration.
- ![image](https://github.com/user-attachments/assets/66b12d50-3d74-446b-bd1c-5424bfd20622)


### Interface Connections

- **Gig0/0/0**: Connects to the internet.
- **Gig0/0/1**: Connects to the firewall.

### Devices and Segments

- **Gig1/1**: Connected to the router.
- **Gig1/2**: Connected to the RADIUS server.
- **Gig1/3**: Connected to the SIEM environment.
- **Gig1/4**: Connected to the DMZ.
- **Gig1/5**: Connected to the inside network (most secure network).
- **Gig1/6**: Security Onion (IDS/IPS).

---

## Network Segmentation

The network is segmented into VLANs for improved security and manageability, including:

- **Inside Network** (Most Secure)
- ![image](https://github.com/user-attachments/assets/c4db1331-9566-4b51-8124-a8a4f5c9bc8e)

- **SIEM (Security Information and Event Management) Network**
- ![image](https://github.com/user-attachments/assets/e8e12182-81aa-4760-82bf-9ef46b3d1ada)

- **RADIUS Server Network**
- ![image](https://github.com/user-attachments/assets/de89f6a0-dae2-4859-83f5-7162b49c8965)

- **Security Onion Network** (for IDS/IPS)
- ![image](https://github.com/user-attachments/assets/4d2ed6ea-f336-4ae4-b059-515e8b60365c)

- **DMZ (Demilitarized Zone)**
- ![image](https://github.com/user-attachments/assets/c62760b3-033a-4e34-8962-807a8eda7dd2)


---

## IP Allocation

IP addresses are allocated efficiently using **VLSM (Variable Length Subnet Mask)** within the LearnSec.local Class C IP range (192.168.1.0/24). VLSM allows each subnet to have a custom subnet mask to reduce network congestion and waste.

**IP Allocation Table:**

| Device Name         | Interface   | IP Address       | Subnet Mask         |
|---------------------|-------------|------------------|---------------------|
| Router              | gig0/0/1    | 192.168.1.97     | 255.255.255.252     |
| Firewall            | gig1/1      | 192.168.1.98     | 255.255.255.252     |
| RADIUS              | gig1/2      | 192.168.1.101    | 255.255.255.252     |
| SIEM                | gig1/3      | 192.168.1.33     | 255.255.255.224     |
| DMZ                 | gig1/4      | 10.0.0.1         | 255.255.0.0         |
| Inside Network      | gig1/5      | 192.168.1.1      | 255.255.255.224     |
| Security Onion      | gig1/6      | 192.168.1.109    | 255.255.255.252     |
| Web Server          | ethernet    | 10.0.0.2         | 255.255.0.0         |
| Radius Server       | ethernet    | 192.168.1.102    | 255.255.255.252     |
| Security Onion      | ethernet    | 192.168.1.110    | 255.255.255.252     |
| Inside Network      | ethernet    | DHCP (192.168.1.1-192.168.1.30) | 255.255.255.224 |
| SIEM Network        | ethernet    | DHCP (192.168.1.34-192.168.1.62) | 255.255.255.224 |

---

## Conclusion

This article provides a foundational secure network design for an eLearning platform using Cisco Packet Tracer. The next step is to configure the network devices to implement the security principles outlined above. Stay tuned for a follow-up article on router configuration and internet connectivity!

**Be SAFE, HAPPY HACKING!**

---

This project is designed and owned by **Jay Patel**.
