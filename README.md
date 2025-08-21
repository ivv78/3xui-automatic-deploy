# Run ansible playbook ONLY ON CLEAN SERVERS (with configured ssh connection). If you have running docker containers or prometheus, or grafana monitoring, save them before running this repository.

# 3x-UI Deployment with Monitoring

Automated deployment of 3x-UI VPN server with Prometheus and Grafana monitoring.

# Quick Start

1. Clone the repository

2. Copy configuration examples:
   ```bash
   cp ansible/inventory/hosts.example ansible/inventory/hosts.yml
   cp ansible/group_vars/all.example ansible/group_vars/all.yml

3. Edit the configuration files with your settings

4. Run the playbook:
   ansible-playbook -i ansible/inventory/hosts.yml ansible/playbook.yml --ask-become-pass

# Access

    3x-UI Panel: https://your-server-ip:2053

    Prometheus: http://your-server-ip:9090

    Grafana: http://your-server-ip:3000

# Features

    VPN server with 3x-UI

    System metrics monitoring with Node Exporter

    Traffic usage statistics

    Connection monitoring

    Automated SSL certificate management
