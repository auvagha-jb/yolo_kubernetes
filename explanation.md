# Yolo with Ansible

This project contains: 
- A Vagrantfile for setting up and configuring the virtual machines 
- An Ansible playbook for setting up and configuring the application in the VMs

## Prerequisites

- [Vagrant](https://developer.hashicorp.com/vagrant/docs/installation) 
- [Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html).

## Description

### Vagrantfile
- Sets up the `geerlingguy/ubuntu2004` virtual machines. 
- Sets the IP and host names.
- Forwards the ports 8000 and 3000 from the VMs to the host so that the client can communicate with the backend from our browser on localhost port 3000

### Ansible playbook

- Roles

  - docker-role   =>  Installs docker, creates a custom network and a volume for data persistence.
                      This spins up the docker, and the database using the `mongo:latest` image.
  
  - backend-role  =>  Building the backend container.
                      This spins up the backend using the backend image to setup and run the backend container. 
  
  - client-role   =>  Builds the client container.
                      This spins up the client using the client image to setup and run the client container.

## Running the application

In the root folder of the project:  
Execute `vagrant up` to setup the VMs and provision ansible configuration using `playbook.yml`.

View the application on your browser running on localhost port 3000