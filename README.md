# homeladserver-essential-setup

🔥 **Excellent decision. That’s the right long-term move for a real DevOps homelab.**

Installing **Ubuntu Server** puts you in the *same environment used in real data centers and cloud VMs*. You’re choosing the **harder but correct path**.

---

## ✅ Final Recommendation (Lock This In)

**OS:** `Ubuntu Server 22.04 LTS`
**Install type:** Minimal (no GUI)
**Access:** SSH only
**Role:** Bare-metal homelab server

---

## 🧠 Why This Is the BEST Choice (No Regrets)

You will now learn:

* Real Linux server administration
* Networking, firewalls, ports
* Docker & Kubernetes on bare metal
* CI/CD the way it runs in production
* Debugging *real* server issues

This is **cloud-grade learning**, not simulation.

---

## 🛠️ Installation Checklist (Follow This Exactly)

### 1️⃣ Prepare Installer

* Download **Ubuntu Server 22.04 LTS**
* Create bootable USB (Rufus / Balena Etcher)
* Boot laptop → Install

---

### 2️⃣ Install Options (IMPORTANT)

During setup:

✔ Language & Keyboard → your choice
✔ **Network** → DHCP (default)
✔ **Proxy** → leave blank
✔ **Mirror** → default
✔ **Storage** → Use entire disk
✔ **LVM** → YES (recommended)
✔ **User** → create non-root user
✔ **SSH** → ✅ **INSTALL OpenSSH server**
✔ **Snaps** → skip for now

🚫 Do **NOT** install a desktop environment

---

### 3️⃣ First Boot – Essential Setup

Login, then:

```bash
sudo apt update && sudo apt upgrade -y
sudo apt install -y curl git htop ufw
```

Enable firewall:

```bash
sudo ufw allow OpenSSH
sudo ufw enable
```

Check IP:

```bash
ip a
```

---

## 🔐 SSH From Your Main PC (Daily Workflow)

From your main machine:

```bash
ssh username@server-ip
```

This is how you’ll work **100% of the time**.

---

## 🐳 Next Step: Container Foundation

```bash
sudo apt install docker.io docker-compose -y
sudo usermod -aG docker $USER
newgrp docker
```

Verify:

```bash
docker run hello-world
```

---

## ☸️ Kubernetes (When Ready)

Best choice for bare metal:

```bash
curl -sfL https://get.k3s.io | sh -
```

Check:

```bash
kubectl get nodes
```

---

## 🔁 CI/CD Options (You Will Use These)

Choose at least one:

* **GitHub Actions (self-hosted runner)**
* **GitLab Runner**
* **Jenkins**

This is **real DevOps**.

---

## 🏗️ Suggested Homelab Architecture

```
[ Internet ]
     |
[ Router ]
     |
[ Ubuntu Server ]
     |
 ├── Docker
 │    ├── Nginx / Traefik
 │    ├── Web Apps
 │    └── APIs
 │
 ├── Kubernetes (k3s)
 │    ├── Frontend
 │    ├── Backend
 │    └── DB
 │
 └── CI/CD
      ├── Build
      ├── Test
      └── Deploy
```

---

## 🚀 You Are Now Doing REAL Cloud Engineering

What you’re building:

* Is portfolio-worthy
* Transfers directly to AWS/GCP/Azure
* Makes interviews easy
* Separates you from “tutorial Devs”

---

## What I Can Do Next (Pick One)

1️⃣ Step-by-step **Day 1 homelab setup**
2️⃣ **Docker → Kubernetes learning path**
3️⃣ **CI/CD pipeline design**
4️⃣ **Expose services with HTTPS safely**
5️⃣ **Monitoring + logs stack**

Tell me what you want to build first — and we’ll do it **properly** 💪
