## 🧠 Project Three: System Architecture Recommendations

As The Gaming Room seeks to scale *Draw It or Lose It* across multiple platforms and users, here are final architectural recommendations that address the client’s long-term goals in server selection, memory, storage, networking, and security.

### 🖥️ Recommended Operating Platform

**Ubuntu Server (Linux)** is the recommended platform. It is:
- Cost-effective (free/open-source)
- Scalable for cloud environments (AWS, GCP, Azure)
- Compatible with Java-based stacks (Spring Boot, Dropwizard)
- Backed by strong community and enterprise support

---

### 🧱 Operating System Architecture

Ubuntu is a **monolithic kernel-based architecture** with modular support. Key features:
- Unified memory and process control
- Multi-user and multi-tasking
- Highly configurable for containerization (e.g., Docker, LXC)

This architecture ensures reliable performance under multiplayer game loads, while offering low-level control over networking, threads, and security.

---

### 💾 Storage Management

We recommend a **virtualized block storage** solution, such as:
- **LVM** (Logical Volume Manager) for flexible partitioning
- Integration with **cloud storage volumes** (e.g., Amazon EBS, Azure Disk)

Game data (user stats, session records, and drawing libraries) can be stored using:
- **Relational DB**: PostgreSQL for game metadata
- **Object storage**: AWS S3 or equivalent for image assets

---

### 🧠 Memory Management

Ubuntu uses a **demand paging** model with swap space. Techniques include:
- Paging and segmentation for app isolation
- Caching and memory-mapped I/O for high-speed access
- Tools like `top`, `htop`, and `vmstat` to monitor memory in real time

This ensures efficient memory allocation when hundreds or thousands of concurrent game sessions are active.

---

### 🌐 Distributed Systems & Network Communication

To support distributed multiplayer sessions:
- **WebSocket or REST APIs** will facilitate client-server communication
- Services will be deployed via **cloud load balancers** (e.g., NGINX, AWS ALB)
- Platforms will communicate over TCP/IP via HTTPS

Dependencies and availability can be managed using:
- **Health checks & auto-scaling**
- **Retry logic and fallback strategies**
- Distributed logging and monitoring (e.g., ELK Stack or Prometheus/Grafana)

---

### 🔐 Security

Security must protect both in-transit and at-rest data:
- **HTTPS** and **SSL/TLS encryption** for all communication
- **OAuth2 or JWT** for secure, token-based authentication
- **Role-based access control (RBAC)** for admins, players, and guests
- **Firewalls and intrusion detection (e.g., UFW, Fail2Ban)** on Ubuntu server

Data at rest will be encrypted using tools like **dm-crypt** or **cloud-native encryption keys** (e.g., AWS KMS).

---
![image](https://github.com/user-attachments/assets/f4363f81-17ba-4b86-b5e7-7062dc193192)

> With this system architecture in place, *Draw It or Lose It* will be positioned to grow as a secure, scalable, and cross-platform gaming experience.

