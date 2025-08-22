# Automated deployment of 3x-UI VPN server with Prometheus and Grafana monitoring.

Run ansible playbook on new, empty server. If you have active docker containers, prometheus, grafana monitoring, save them before running this repository.

# Quick Start

1. Clone the repository

2. Copy configuration examples:
 
   cp ansible/inventory/hosts.example ansible/inventory/hosts.yml
   
   cp ansible/group_vars/all.example ansible/group_vars/all.yml

3. Edit the configuration files with your settings

4. Run the playbook (All ansible playbooks are running through SSH connection, private key file directory specified in hosts.yml "ansible_ssh_private_key_file"):
   
   ansible-playbook -i ansible/inventory/hosts.yml ansible/playbook.yml --ask-become-pass

# Access

    3x-UI Panel: https://your-server-ip:2053

    Prometheus: http://your-server-ip:9090

    Grafana: http://your-server-ip:3000

!panel.png !dashboard1.png !dashboard2.png

# Features

    VPN server with 3x-UI

    System metrics monitoring with Node Exporter

    Traffic usage statistics

    Connection monitoring

    Automated SSL certificate management
