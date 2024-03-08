#Author: MEZZOUR Omar

# Ansible Project

This Ansible project is designed to configure and deploy a multi-server environment with web, database, and logging servers. The project utilizes Vagrant for local testing and Ansible for configuration management.

## Project Structure

The project is organized as follows:

- **Vagrantfile**: Defines the Vagrant environment setup, including virtual machine configurations.
- **ansible.cfg**: Ansible configuration file.
- **inventories/hosts.ini**: Ansible inventory file containing server definitions.
- **inventories/group_vars/common_settings.yml**: Common settings for all servers.
- **keyansible/keyansible**: Private SSH key for Ansible.
- **keyansible/keyansible.pub**: Public SSH key for Ansible.
- **web_app_servers**: Directory for the web application servers.
- **db_server**: Directory for the database server.
- **logging_server**: Directory for the logging server.

Each server directory contains an Ansible playbook (`*_playbook.yml`) and a `roles` directory with specific roles for configuration.

## Getting Started

Follow these steps to deploy the project:

1. **Install Dependencies:**
   - Install [Vagrant](https://www.vagrantup.com/docs/installation).
   - Install [VirtualBox](https://www.virtualbox.org/wiki/Downloads).
   - Install [Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html).

2. **Clone the Repository:** # this step will be activated after loading the last version of the project into github.
   ```bash
   git clone <repository_url>
   cd Ansible-Project


1- Configure Ansible:
    Adjust configurations in ansible.cfg if needed.
    Update inventories/hosts.ini with the IP addresses of your servers.
    
2- Run Vagrant:
   user@linux-$ vagrant up # then press enter
   
3- Run Ansible Playbooks:
user@linux$ ansible-playbook -i inventories/hosts.ini web_app_servers/ansible/user@linux$ web_app_server_playbook.yml
user@linux$ ansible-playbook -i inventories/hosts.ini db_server/ansible/db_server_playbook.yml
user@linux$ ansible-playbook -i inventories/hosts.ini logging_server/ansible/logging_server_playbook.yml


Notes

    1- Customize the server configurations and roles according to your requirements.
    2- Ensure your system meets the hardware and software requirements for running Vagrant and VirtualBox.
    3- Update IP addresses and server names in the inventories/hosts.ini file for accurate Ansible inventory.

Feel free to reach out for any issues or further assistance; contact infos: omar.mezzour@eidia.ueuromed.org
