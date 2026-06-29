# ☁️ Secure and High-Performance Cloud Infrastructure on Microsoft Azure

> Design and deployment of a secure enterprise cloud infrastructure on Microsoft Azure integrating centralized identity management, Zero-Trust networking, monitoring, SIEM/XDR, collaboration services and perimeter security.

![Azure](https://img.shields.io/badge/Microsoft%20Azure-Cloud-0078D4?logo=microsoftazure)
![Ubuntu](https://img.shields.io/badge/Ubuntu-22.04-E95420?logo=ubuntu)
![Docker](https://img.shields.io/badge/Docker-2496ED?logo=docker)
![FortiGate](https://img.shields.io/badge/FortiGate-NGFW-red)
![Wazuh](https://img.shields.io/badge/Wazuh-SIEM-green)
![Zabbix](https://img.shields.io/badge/Zabbix-Monitoring-red)

---

# 📖 Project Overview

This project was carried out as part of my final-year project (PFE).

The objective was to design and deploy a secure, monitored and collaborative cloud infrastructure on Microsoft Azure using open-source and enterprise technologies.

The infrastructure provides:

- Secure remote access through a Mesh VPN
- Centralized identity management (SSO)
- Infrastructure monitoring
- Threat detection (SIEM/XDR)
- Secure file sharing
- Helpdesk platform
- DNS protection
- Next Generation Firewall

---

# 🏗️ Infrastructure Architecture

## Global Architecture

![Architecture](architecture)

---

## Network Topology

![Topology](Images/architecture-réseau.png)

---

## Full Mesh VPN Topology

![Mesh](Images/Mesh-Topologie.png)

---

# 🔐 Infrastructure Components

## 🔥 FortiGate NGFW

- Network perimeter protection
- Routing
- NAT
- Firewall policies
- Traffic inspection

![FortiGate](Images/Frotigate-dashbord.png)

---

## 🌐 NetBird (WireGuard Mesh VPN)

Secure communication between every virtual machine through a Full Mesh VPN based on WireGuard.

![NetBird](Images/Netbird-dashbord.png)

---

## 📊 Zabbix Monitoring

Infrastructure monitoring including:

- Linux servers
- Windows servers
- FortiGate
- Network availability
- Performance dashboards

![Zabbix](Images/Zabbix-dashbord.png)

Additional monitoring view:

![Hosts](zabbix-hosts)

---

## 🛡️ Wazuh SIEM / XDR

Centralized security monitoring including:

- Log collection
- Threat detection
- File Integrity Monitoring
- Security alerts

![Wazuh](Images/Wazuh-dashbord.png)

---

## 👤 Authentik

Centralized Identity Provider implementing:

- Single Sign-On
- Identity Management
- OAuth2 / OpenID Connect

![Authentik](Images/Authentik-dashbord .png)

---

## ☁️ Cloudflare

Cloudflare is used for:

- DNS Management
- SSL/TLS
- DNSSEC
- Secure public access

![Cloudflare](Images/cloudflare-dashbord.png)

---

## 📁 Nextcloud

Collaborative platform providing:

- File storage
- File sharing
- Team collaboration

![Nextcloud](Images/nextcloud-dashbord.png)

---

## 🎫 Zammad

Helpdesk platform providing:

- Ticket management
- Incident tracking
- User support

![Zammad](Images/Zammad-dashbord.png)

---

## 🔑 VPN Server

VPN Gateway used to interconnect the infrastructure securely.

![VPN](Images/Vpn-Server.png)

---

# 🛠️ Technologies

| Category | Technologies |
|------------|--------------|
| Cloud | Microsoft Azure |
| Operating Systems | Ubuntu 22.04, Rocky Linux |
| Firewall | FortiGate |
| VPN | NetBird, WireGuard |
| Monitoring | Zabbix |
| SIEM/XDR | Wazuh |
| IAM | Authentik |
| Collaboration | Nextcloud |
| Helpdesk | Zammad |
| DNS Security | Cloudflare |
| Containers | Docker, Docker Compose |

---

# 🎯 Implemented Features

- Secure Full-Mesh VPN
- Centralized Monitoring
- SIEM / XDR
- Identity Management (SSO)
- Secure File Sharing
- Ticket Management
- DNS Protection
- Next Generation Firewall
- Cloud Infrastructure on Microsoft Azure

---

# 📄 Documentation

The complete project documentation is available in the **docs** folder.

📄 **PFE_Infrastructure_Cloud.pdf**

> **Note:** GitHub cannot preview the PDF because it exceeds the maximum preview size. Please download the file to view the complete documentation.

---

# 👩‍💻 Author

**Salma Ouchahed**

- LinkedIn: https://www.linkedin.com/in/salma-ouchahed-652189206/
- GitHub: https://github.com/CyberTechSali

---

# 📜 License

This project was developed for educational and portfolio purposes.

All software and technologies remain subject to their respective licenses.
