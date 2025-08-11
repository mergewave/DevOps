# Ansible

## Overview
Ansible is an open-source IT automation tool that lets you describe how your infrastructure and applications should be configured, deployed, and managed — all in plain text (YAML) without needing to install agents on your servers.

Think of it as a way to say:

> “Hey, set up my servers exactly like this, install these packages, deploy this app, and make sure it stays that way.”

…and Ansible will do it for you — consistently, across hundreds (or thousands) of machines.

---

## Key Points
- **Agentless** → Works over SSH (Linux) or WinRM (Windows), so you don’t need special software on target machines.
- **Idempotent** → Running the same playbook twice won’t break things; it only applies changes if needed.
- **Declarative style** → You write what the final state should be, not every single step to get there.
- **Human-readable YAML** → Configuration is written in simple YAML files called playbooks.

---

## Common Uses
- Installing and configuring software
- Deploying applications
- Managing system settings and users
- Orchestrating multi-server workflows (e.g., “deploy backend → then frontend → then run database migrations”)

💡 **In DevOps pipelines**, Ansible often works alongside Docker, Terraform, and CI/CD tools — where Terraform builds the infrastructure, Ansible configures it, and your pipeline ties it all together.

---

## How Ansible Works
```plaintext
+-------------------+       SSH/WinRM       +-------------------+
|   Control Node    |  ------------------>  |  Managed Node 1   |
|  (Runs Ansible)   |                        |  (Server/App)     |
+-------------------+                        +-------------------+
        |                                     
        |------------------>  Managed Node 2
        |                   (Server/App)
        |
        |------------------>  Managed Node 3
                            (Server/App)
