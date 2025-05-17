# Rooman_technology_project
# Rooman_technology_project
Automating Configuration Management with Ansible

Automate and standardize your infrastructure setup using Ansible. This repository provides playbooks, roles, and inventory configurations to deploy and manage web and database servers across staging and production environments.

Table of Contents

Features

Prerequisites

Installation

Configuration

Usage

Project Structure

Testing

Contributing

License

Features

Idempotent Playbooks: Easily rerun without side effects

Modular Roles: Reusable Ansible roles for web and database servers

Multi-Environment: Separate inventories for staging and production

Variable Management: Centralized variable files for easy customization

Prerequisites

Control Node: Linux/macOS with Ansible installed (version >=2.9)

Managed Nodes: SSH-accessible servers (Linux) with Python

Git: For version control

Installation

Clone the repository:

git clone https://github.com/abhinavkumar2119/7.-automating-configuration-management-with-ansible---393a4dfb.git
cd 7.-automating-configuration-management-with-ansible---393a4dfb/Configuration-Management-Automation-with-Ansible-main

Install Ansible (if not already installed):

pip install ansible

Configuration

Inventory Files:

Copy inventory/staging.sample to inventory/staging

Copy inventory/production.sample to inventory/production

Update host IPs or hostnames accordingly

Variable Files (in vars/):

Edit webserver_vars.yml and dbserver_vars.yml to configure ports, users, and other settings

Usage

Deploy to Staging:

ansible-playbook -i inventory/staging playbooks/site.yml

Deploy to Production:

ansible-playbook -i inventory/production playbooks/site.yml

Syntax Check:

ansible-playbook --syntax-check playbooks/site.yml

Dry Run (Check Mode):

ansible-playbook -i inventory/staging playbooks/site.yml --check

Project Structure

ansible/
├── inventory/
│   ├── staging.sample      # Example hosts for staging
│   └── production.sample   # Example hosts for production
├── vars/
│   ├── webserver_vars.yml  # Variables for webserver role
│   └── dbserver_vars.yml   # Variables for dbserver role
├── playbooks/
│   ├── site.yml            # Main orchestrator playbook
│   ├── webserver.yml       # Playbook for web servers
│   └── dbserver.yml        # Playbook for db servers
└── roles/
    ├── webserver/          # Web server installation & config
    └── dbserver/           # Database server installation & config

Testing

Use --diff to preview changes without applying:

ansible-playbook -i inventory/staging playbooks/site.yml --diff

Validate YAML formatting:

yamllint playbooks/ roles/

Contributing

Contributions are welcome! Please read CONTRIBUTING.md for guidelines on setting up your environment, coding standards, and submitting pull requests.
