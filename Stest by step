Perfect.
This is your **Day 1 homelab setup**, written like a **real DevOps runbook**. Follow it in order and you’ll end Day 1 with a **production-style server** ready for Docker, CI/CD, and Kubernetes.

---

# 🧱 DAY 1 HOMELAB SETUP (Ubuntu Server)

**Goal:**
✔ Secure server
✔ Remote access (SSH)
✔ Docker-ready
✔ Proper firewall
✔ Clean baseline for DevOps

---

## 🖥️ PART 1 — Ubuntu Server Installation (Critical Choices)

### 1️⃣ Boot From USB

* Plug in USB
* Power on laptop
* Press `F2 / F12 / ESC / DEL`
* Choose USB device

You should see:

```
Try or Install Ubuntu Server
```

Press **Enter**

---

### 2️⃣ Language, Keyboard

* Language: your choice
* Keyboard: Detect automatically → OK

---

### 3️⃣ Network

* Use **DHCP (default)**
* Confirm you have an IP

⚠️ If no internet → stop and fix before continuing

---

### 4️⃣ Proxy & Mirror

* Proxy: **Leave blank**
* Mirror: **Default**

---

### 5️⃣ Storage (IMPORTANT)

Choose:
✔ **Use entire disk**
✔ **Set up LVM** → YES

Why LVM?

* Resize partitions later
* Real server behavior

---

### 6️⃣ User Setup

Create a **non-root user**:

* Username: `deo` (or anything you want)
* Password: strong password

🚫 Do NOT enable root login

---

### 7️⃣ SSH Setup (MANDATORY)

✔ **Install OpenSSH server**
❌ Import SSH key → skip for now (we’ll add later)

---

### 8️⃣ Snaps

❌ Skip additional snaps

---

### 9️⃣ Finish Install

* Remove USB
* Reboot

---

## 🔐 PART 2 — First Login & Hardening

Login locally or via SSH.

---

### 🔄 Update System

```bash
sudo apt update && sudo apt upgrade -y
sudo reboot
```

---

### 🔥 Firewall (UFW)

```bash
sudo apt install ufw -y
sudo ufw allow OpenSSH
sudo ufw enable
sudo ufw status
```

Expected:

```
Status: active
```

---

### 🧠 System Info Check

```bash
hostnamectl
ip a
df -h
free -h
```

---

## 🔑 PART 3 — SSH Best Practices

From your **main PC**:

```bash
ssh deo@SERVER_IP
```

---

### 🔐 Optional (But Recommended): SSH Keys

On your main PC:

```bash
ssh-keygen
ssh-copy-id deo@SERVER_IP
```

Then on the server:

```bash
sudo nano /etc/ssh/sshd_config
```

Change:

```text
PasswordAuthentication no
PermitRootLogin no
```

Restart SSH:

```bash
sudo systemctl restart ssh
```

---

## 🐳 PART 4 — Docker Installation (Foundation)

### Install Docker

```bash
sudo apt install docker.io docker-compose -y
sudo usermod -aG docker $USER
newgrp docker
```

---

### Verify Docker

```bash
docker run hello-world
```

✅ If it works — Docker is ready.

---

## 📁 PART 5 — Homelab Directory Structure

Create a clean layout:

```bash
mkdir -p ~/homelab/{docker,k8s,cicd,monitoring}
tree ~/homelab
```

You now have:

```
homelab/
├── docker
├── k8s
├── cicd
└── monitoring
```

This mirrors **real infrastructure repos**.

---

## 🌐 PART 6 — Install Nginx (Optional but Useful)

```bash
sudo apt install nginx -y
sudo ufw allow 'Nginx Full'
```

Test:

```bash
curl http://localhost
```

You should see HTML output.

---

## 🧪 PART 7 — Sanity Test (Mini Deployment)

Create a test container:

```bash
docker run -d \
  --name test-nginx \
  -p 8080:80 \
  nginx
```

Test from browser:

```
http://SERVER_IP:8080
```

If it loads — networking works.

---

## 🧠 DAY 1 CHECKLIST (You Should Have)

✔ Ubuntu Server running
✔ SSH access
✔ Firewall enabled
✔ Docker installed
✔ Test container deployed

🔥 This is already **production-grade basics**.

---

## 🚀 What Day 2 Will Add

Next steps:
1️⃣ Docker Compose projects
2️⃣ Reverse proxy (Traefik)
3️⃣ HTTPS (Let’s Encrypt)
4️⃣ CI/CD pipeline
5️⃣ Kubernetes (k3s)

---

## 🧭 Recommended Day 2 Path (Pick One)

Reply with **ONE number**:

**1️⃣ Docker-first path** (best for web apps)
**2️⃣ CI/CD pipeline setup**
**3️⃣ Kubernetes (k3s) install**
**4️⃣ Monitoring stack (Grafana + Prometheus)**

You’re building this **like a real cloud engineer** 💪
