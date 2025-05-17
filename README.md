# Rooman Technology Project: Automating Configuration Management with Ansible

Automate and standardize your infrastructure setup using Ansible. This repo provides playbooks, roles, and inventory configs to deploy and manage web and database servers in both staging and production.

---

## Table of Contents

- [Features](#features)  
- [Prerequisites](#prerequisites)  
- [Installation](#installation)  
- [Configuration](#configuration)  
- [Usage](#usage)  
- [Project Structure](#project-structure)  
- [Testing](#testing)  
- [Contributing](#contributing)  
- [License](#license)  

---

## Features

- **Idempotent Playbooks**: Safely rerun without side effects  
- **Modular Roles**: Reusable Ansible roles for web & DB servers  
- **Multi‑Environment**: Separate staging and production inventories  
- **Centralized Variables**: Easy customization via `vars/`  

---

## Prerequisites

- **Control Node**: Linux/macOS with Ansible ≥ 2.9  
- **Managed Nodes**: SSH‑accessible Linux servers with Python  
- **Git**: For version control  

---

## Installation

1. **Clone the repo**  
   ```bash
   git clone https://github.com/abhinavkumar2119/7.-automating-configuration-management-with-ansible---393a4dfb.git
   cd 7.-automating-configuration-management-with-ansible---393a4dfb/Configuration-Management-Automation-with-Ansible-main
Install Ansible (if needed)

bash
Copy
Edit
pip install ansible
Configuration
Inventory

Copy inventory/staging.sample → inventory/staging

Copy inventory/production.sample → inventory/production

Edit host IPs/hostnames in each file

Variables (vars/)

Update webserver_vars.yml and dbserver_vars.yml

Usage
Deploy to Staging

bash
Copy
Edit
ansible-playbook -i inventory/staging playbooks/site.yml
Deploy to Production

bash
Copy
Edit
ansible-playbook -i inventory/production playbooks/site.yml
Syntax Check

bash
Copy
Edit
ansible-playbook --syntax-check playbooks/site.yml
Dry Run

bash
Copy
Edit
ansible-playbook -i inventory/staging playbooks/site.yml --check
Project Structure
python
Copy
Edit
ansible/
├── inventory/
│   ├── staging.sample      # example staging hosts
│   └── production.sample   # example production hosts
├── vars/
│   ├── webserver_vars.yml  # web server variables
│   └── dbserver_vars.yml   # database variables
├── playbooks/
│   ├── site.yml            # orchestrator playbook
│   ├── webserver.yml       # webserver setup
│   └── dbserver.yml        # db server setup
└── roles/
    ├── webserver/          # webserver tasks
    └── dbserver/           # database tasks
Testing
Preview changes

bash
Copy
Edit
ansible-playbook -i inventory/staging playbooks/site.yml --diff
Validate YAML

bash
Copy
Edit
yamllint playbooks/ roles/
Contributing
See CONTRIBUTING.md for:

Fork & clone steps

Branch naming conventions

Syncing with upstream

PR workflow
