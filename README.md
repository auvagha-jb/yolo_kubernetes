# Yolo Orchestration using GKE

This project is a Node.js, Express API and MongoDB e-commerce feature project.
[App Link](http://34.105.128.4:3000/)

It can be set up and run in multiple ways, including on Google Kubernetes Engine (GKE), in a virtual machine (VM) using Vagrant and Ansible, and directly on a user's computer using Docker and Docker Compose.

When running on GKE, the user needs to have `gcloud` and `kubectl` installed and must authenticate and set their Google Cloud project before deploying the kubernetes manifests using the `kubectl apply -f <manifest-name.yaml>` command. Find a detailed explanation on <a href="https://github.com/ElitepathSoftware/yolo-kubernetes/blob/master/explanation.md">explanation.md</a>

When running in a VM, the user needs to have Vagrant and Ansible installed, and can set up the virtual machine and provision ansible configuration using the command `vagrant up`.

When running directly on a user's computer, the user needs to have Docker and Docker Compose installed. The user can build and run the project using the `docker-compose build` and `docker-compose up` commands, and can access the app at <a href="http://localhost:3000">localhost port 3000</a>.

The links to the docker images can be found below:
- <a href="https://hub.docker.com/repository/docker/jerryauvagha/yolo_client" target="blank">Client Image</a> docker image
- <a href="https://hub.docker.com/repository/docker/jerryauvagha/yolo_backend" target="blank">Backend Image</a> docker image