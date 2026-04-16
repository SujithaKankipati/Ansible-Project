# 🚀 Automated Multi-Tier Infrastructure Deployment using Ansible

## 📌 Project Overview

This project demonstrates automated provisioning of a multi-tier web application infrastructure using Ansible. It sets up a web server and a database server using a modular, role-based architecture.

---

## 🏗️ Architecture

Client (Browser)
        ↓
Web Server (Apache)
        ↓
Database Server (MySQL)

* **Web Server**: Hosts the website using Apache
* **Database Server**: Runs MySQL for backend storage
* **Control Node**: Executes Ansible playbooks to configure servers

---

## 🧰 Technologies Used

* Ansible (Automation)
* Linux (Ubuntu)
* Apache HTTP Server
* MySQL
* YAML (Playbooks)
* Jinja2 (Templates)
* AWS EC2 (for hosting)

---

## 📁 Project Structure

Ansible-Project/
│
├── inventory/
│   ├── .gitignore
│   └── hosts.ini.example
│
├── group_vars/
│   └── all.yml
│
├── roles/
│   ├── common/
│   ├── web/
│   ├── db/
│   └── app/
│
├── site.yml
└── README.md

## ⚙️ Roles Description

### 🔹 common

* Updates package cache
* Installs basic utilities (curl, git)

### 🔹 web

* Installs Apache
* Starts and enables Apache service

### 🔹 db

* Installs MySQL
* Starts and enables MySQL service

### 🔹 app

* Deploys website using Jinja2 template
* Places `index.html` in `/var/www/html`

---

## 🔐 Security Best Practices

* Actual inventory file (`hosts.ini`) is **not committed**
* Sensitive data like IP addresses are excluded using `.gitignore`
* A sample file (`hosts.ini.example`) is provided for reference

---

## 📄 Sample Inventory File

[web]
<web-server-ip>

[db]
<db-server-ip>

---

## 🚀 How to Run the Project

### 1. Clone the repository

git clone https://github.com/SujithaKankipati/Ansible-Project.git
cd Ansible-Project

### 2. Create your inventory file

cp inventory/hosts.ini.example inventory/hosts.ini
Update it with your server IPs.

### 3. Run the playbook

ansible-playbook -i inventory/hosts.ini site.yml

## 🌐 Output

Access the application in your browser:
http://<web-server-public-ip>

You should see:
My Ansible Project
Deployed using Ansible

## 🧠 Concepts Demonstrated

* Ansible Playbooks
* Role-based architecture
* Inventory management
* Idempotent automation
* Jinja2 templating
* Multi-tier architecture deployment

---

## ⚠️ Notes

* The application is served over HTTP (port 80), so the browser may show "Not Secure"
* HTTPS can be enabled using SSL certificates (e.g., Let's Encrypt) for production use

---

## 🎯 Key Highlights

* Automated infrastructure provisioning
* Clean and modular code structure
* Secure handling of sensitive configuration
* Real-world DevOps practices

---
