# Cloud SOC & Adversary Emulation Lab (Elastic + Mythic C2)

## Objective
The objective of this project is to build a cloud-native Security Operations Center (SOC) environment hosted on Vultr VPS infrastructure. By deploying an Elastic Stack SIEM with a centralized Fleet Server, I established automated log ingestion pipelines for Windows (RDP) and Linux (SSH) endpoints. The lab focuses on simulating advanced cyber attacks using the Mythic C2 framework, detecting adversarial behaviors through Elastic Defend agents, and orchestrating incident response workflows via osTicket integration.

### Skills Learned
- **Cloud Infrastructure & Networking:** Deploying VPCs, cloud instances, and secure access lists in a public cloud provider (Vultr).
- **Centralized Endpoint Management:** Deploying and managing Elastic Agents via a dedicated Fleet Server.
- **Command & Control (C2) Architecture:** Understanding external adversarial infrastructure using Mythic C2 to control compromised assets.
- **Incident Management & Ticketing:** Implementing osTicket to simulate life-cycle alert triage, case management, and documentation workflows for SOC analysts.

### Tools used
- **SIEM & Ingestion:** Elastic Server & Kibana (`172.31.0.0/24` Private Network).
- **Endpoint Orchestration:** Elastic Fleet Server managing Windows Server and Ubuntu Server endpoints.
- **Ticketing & Case Management:** osTicket Server integrated with Elastic alert forwarding.
- **Adversarial Emulation:** Kali Linux & Mythic C2 Server.
- **Cloud Hosting:** Vultr Cloud Compute (VPC Network Cloud).

---

## Network Architecture & Data Flow

The environment maps out a realistic corporate cloud deployment (VPC) targeted by external threats, monitored remotely by a SOC Analyst.

<img width="1182" height="1112" alt="image" src="https://github.com/user-attachments/assets/6a5885a1-1232-47c9-815e-9312cee363c4" />


---

## Lab Implementation Roadmap

### 1. Cloud Infrastructure Provisioning (Vultr)
- Deployment of the Virtual Private Cloud (VPC) on `172.31.0.0/24`.
- Provisioning instances for the Elastic Stack, osTicket Server, Windows Server (RDP enabled), and Ubuntu Server (SSH enabled).

### 2. SIEM Deployment & Fleet Configuration
- Installation and configuration of Elastic Server and Kibana.
- Setting up the **Fleet Server** to act as the centralized controller for security agents.
- Installing the **Elastic Agent** on endpoints to securely forward telemetry to the SIEM.

### 3. C2 Infrastructure & Attack Simulation
- Setting up the **Mythic C2 Server** on an external instance.
- Simulating initial access, payload delivery, and command orchestration against the cloud targets.

### 4. Detection Engineering & Incident Ticketing
- Building detection rules within Elastic to flag malicious RDP/SSH activity and C2 implants.
- Configuring automated alert forwarding from Elastic into **osTicket** to simulate real analyst ticket lifecycles.
