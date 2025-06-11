# 📘 Cloud Fundamentals
> This repository explains essential cloud and DevOps concepts in a structured and professional manner, suitable for engineers transitioning into cloud-native practices or aiming to build a rock-solid foundational understanding.

## 🧠 DevOps vs. Cloud
* **Cloud** is digital transformation — renting compute, storage, and services.
* **DevOps** is automation — enabling faster releases and fewer human errors.
* DevOps allows more client feedback and faster iteration through CI/CD and infrastructure-as-code.

## ⚙️ Over-Subscription Explained
**Over-Subscription (Overcommitment):** allocating more virtual resources than physical capacity.

**Ratio Format (N\:M):**

* `N` = Number of Virtual Machines
* `M` = Number of Physical Servers

### 🔹 1:1 (Not Over-Subscription)
* Fully dedicated physical resources
* No contention, no performance impact
* Example: 2 VMs each mapped to one physical server

### 🔹 2:1 (Over-Subscription)
* Two VMs share one server’s resources
* Risk of degraded performance under load
* Effective resource use, but trade-off on reliability

### 🔹 1:2 (HA Setup, Not Over-Subscription)
* Single VM split across two servers for redundancy
* Improves fault tolerance

## 🏢 On-Prem vs Cloud
* **On-Premises:** Your own hardware, full control, full responsibility.
* **Dedicated Cloud (e.g., AWS Outposts):** Provider-owned hardware at your site, but managed by provider.

### 🔹 CAPEX vs OPEX
* **CAPEX:** Capital Expenditure – own hardware, long-term investment
* **OPEX:** Operational Expenditure – pay-as-you-go, service-based

## 🧭 From Data Center to Cloud
A data center becomes a cloud when it’s abstracted via orchestration + automation platforms (e.g., AWS Console, Azure Portal).

## 🆚 AWS Console vs Azure Portal

| Feature     | AWS Management Console         | Azure Portal          |
| ----------- | ------------------------------ | --------------------- |
| UI Design   | Menu-based                     | Tile-based            |
| IAM System  | AWS IAM                        | Azure AD + RBAC       |
| Cost Tools  | Cost Explorer                  | Azure Cost Management |
| IaC Support | CloudFormation, CDK, Terraform | ARM, Bicep, Terraform |

## 🌍 Cloud Specialties
* **Azure** → Enterprise integration (M365)
* **AWS** → Scalable services & eCommerce
* **Google Cloud** → AI & analytics
* **IBM Cloud** → Mainframe systems

## 🔀 Hybrid & Multi-Cloud
Use multiple clouds with sensitive data kept on-prem (Hybrid).

## 🧪 Agile vs Waterfall vs DevOps
* **Agile:** Iterative development, short feedback cycles
* **Waterfall:** Linear, sequential
* **DevOps:** Enables Agile with automation, CI/CD, and monitoring

## 🚀 CI/CD Explained
* **CI:** Code is built and tested automatically
* **CD: Continuous Delivery:** Needs manual approval
* **CD: Continuous Deployment:** Auto-deploy to production after tests

> 99% of traditional companies still deploy at low-traffic windows (e.g., 2AM–4AM weekends).

> Modern systems use feature flags, canary releases, and automated rollbacks.

## 🔁 Modern Rollback Strategies
1. **Feature Flags** — Toggle features instantly
2. **Blue-Green** — Swap environments
3. **Canary** — Gradual rollout
4. **Shadow** — Parallel testing without user impact

## 🧱 CNCF Cloud Native Principles
Cloud-native = Containers, microservices, immutable infrastructure, autoscaling

## 🌐 TCP/IP & Subnetting Basics
* **CIDR Notation:** `/24`, `/16`, etc. → indicates subnet size
* **Network vs Host Portion:** determined by subnet mask
* **Broadcast Address:** last IP in range used to reach all hosts

### Examples:
* **Class C (/24)**

  * IP: `192.168.1.10/24`
  * Network: `192.168.1.0`
  * Broadcast: `192.168.1.255`
  * Usable Hosts: `192.168.1.1 – 192.168.1.254`

* **Class B (/16)**

  * IP: `172.16.5.20/16`
  * Network: `172.16.0.0`
  * Broadcast: `172.16.255.255`
  * Usable Hosts: `172.16.0.1 – 172.16.255.254`

* **Class A (/8)**

  * IP: `10.1.2.3/8`
  * Network: `10.0.0.0`
  * Broadcast: `10.255.255.255`
  * Usable Hosts: `10.0.0.1 – 10.255.255.254`

* **Custom Subnet (/22)**

  * IP: `192.168.4.10/22`
  * Network: `192.168.4.0`
  * Broadcast: `192.168.7.255`
  * Usable Hosts: `192.168.4.1 – 192.168.7.254`

* **Smallest Subnet (/30)**

  * IP: `192.168.1.5/30`
  * Network: `192.168.1.4`
  * Broadcast: `192.168.1.7`
  * Usable Hosts: `.5 and .6` → perfect for router-to-router link

### Concepts Summary:
* **Subnet Mask:** defines network vs host portions
* **Network Address:** first IP in the range (not assignable)
* **Broadcast Address:** last IP, used to reach all hosts
* **CIDR Efficiency:** /30 for P2P, /16 for larger orgs

## 🔌 Private IP Ranges
* `10.0.0.0/8`, `172.16.0.0/12`, `192.168.0.0/16` — Not routable on internet

## 🌐 Web App, Client, Server
* **Web App:** Hosted app (static/dynamic)
* **Client:** Device/browser accessing the app
* **Web Server:** Delivers content (Apache, Nginx, IIS)

## 🔀 Middleware Overview
* Acts as a bridge (e.g., API Gateway, ESB)
* Adds security, scalability, caching, authentication (OAuth, JWT, etc.)

## ⚙️ GPU Role in Cloud
Used in AI/ML training, parallel processing, and rendering workloads.

## 🏗️ Cloud Infrastructure Hierarchy

| Layer               | Distance           | Purpose                               |
| ------------------- | ------------------ | ------------------------------------- |
| Region              | 100–500 miles      | Major area (e.g., us-east-1)          |
| Availability Zone   | 5–25 miles apart   | Fault isolation                       |
| Local Zone          | 50–200 miles       | Low-latency access near urban centers |
| Data Center         | Core physical site | Actual compute infrastructure         |
| Edge Location (CDN) | Worldwide, global  | Content caching & delivery            |

> 🔹 AWS Direct Connect = Fiber cable → low-latency, secure

> 🔹 AWS Wavelength = Edge for 5G deployments

## 🔐 VPN vs Direct Connect

| Feature  | VPN               | Direct Connect              |
| -------- | ----------------- | --------------------------- |
| Medium   | Public Internet   | Private Line (Fiber, MPLS)  |
| Latency  | Higher (variable) | Lower (1–10 ms typical)     |
| Security | Encrypted tunnel  | Physically isolated, secure |

## 📌 Summary
You’ve now mastered:

* Cloud architecture, models & infra layers
* DevOps principles and SDLC integration
* Networking, IP classes, CIDR, and HA
* Modern deployment and rollback strategies
* Real-world tooling used across providers

> 📍Next Step: 
🧠 *Want more? Follow this repo and explore the full DevOps knowledge base at* **[AIOps Vision](https://github.com/AIOps-Vision)**.
