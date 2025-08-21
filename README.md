# Automated Deployment of x-ui with Monitoring

This repository contains Ansible playbooks and GitHub Actions workflow to deploy x-ui VPN service along with Prometheus and Grafana for monitoring.

# Prerequisites

- A server with SSH access (Ubuntu 20.04/22.04 recommended)
- SSH private key for accessing the server
- Fork this repository

# Setup

1. Clone your forked repository:
 
   git clone https://github.com/ivv78/3xui-automatic-deploy.git
   cd your-project-repo

2. Prepare inventory file
 
   cd ansible/inventory
   cp hosts.example production

   Edit production and replace the example IP with your server's IP

3. Prepare variables file:
 
   cd ../group_vars
   cp all.example all.yml

   Edit all.yml and set your values for passwords, ports, etc.

4. Set up GitHub Secrets:

   Go to your repository settings on GitHub.

   Navigate to "Secrets and variables" > "Actions".

   Add the following secrets:

   SSH_PRIVATE_KEY - your SSH private key for server access

   SERVER_IP - your server IP address

5.  Run the deployment:

   Go to the "Actions" tab of your repository.

   Select "Deploy Infrastructure with Ansible".

   Click "Run workflow".


# Access Services

After deployment, you can access:

    x-ui panel: http://your-server-ip:54321

    Prometheus: http://your-server-ip:9090

    Grafana: http://your-server-ip:3000 (admin/your_password)

# Notes

    The files inventory/production and group_vars/all.yml are ignored by Git to prevent accidental exposure of sensitive data.

    Make sure your server has a firewall allowing ports for x-ui (54321), Prometheus (9090), and Grafana (3000).

