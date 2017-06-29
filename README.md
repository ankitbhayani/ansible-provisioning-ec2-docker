# Provision Docker with Ansible on EC2

This playbook allows you to provision a docker on Amazon EC2. The deploy.yml playbook creates a swarm-admin instance, as the control point for the swarm, and a consul node for key/value needed for docker networking.

### Requirements
   * Ansible 1.9+
   * python >= 2.6
   * boto

### Environment Variables
EVs for provisioing on EC2 are located at `vars/external_vars.yml`. Docker-Machine, used to create the swarm, needs a couple extra EVs for provisioning a swarm. Add your specifcs to this file.

### What it does
Running the playbook: `$ ansible-playbook deploy.yml` does the following:

1. Creates  an instance called "Admin-Swarm" with the security group, "swarm-admin".
1. Installs Docker-Engine, Docker-Machine and Docker-Compose on the Admin-Swarm node
1. Runs tasks such as docker and compose
