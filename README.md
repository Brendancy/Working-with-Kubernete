# Working-with-Kubernete
- Learn how to utilize Kubernetes in a laboratory setting by employing Minikube within a VMware Workstation environment running on Ubuntu 23.04. This guide will walk you through the steps to set up and leverage Kubernetes for your testing and development needs.

# Setting Up Kubernetes on VMware Workstation  
- This repository provides a guide on configuring Kubernetes on VMware Workstation for local development and testing purposes. The following steps will guide you through the process of setting up a Kubernetes cluster on your VMware Workstation virtual machines.
# Prerequisites  
## VMware Workstation: 
Ensure that you have VMware Workstation installed on your machine.

## Virtual Machines: 
Create virtual machines for the Kubernetes cluster nodes (master and worker nodes). These VMs should have sufficient resources allocated for Kubernetes to run smoothly.

# Kubernetes Tools:  
- kubectl: Kubernetes command-line tool.
- kubeadm: Tool for bootstrapping Kubernetes clusters.
- Kubelet: Component that runs on all machines in the cluster.
Install these tools on each virtual machine.
# Step 1: Update and upgrade your Linux VM  
       sudo apt update && sudo apt upgrade -y  
- the above command line  updates the package information on your system and then upgrades the installed packages to their latest versions, automatically confirming any prompts that may arise during the upgrade. This helps ensure that your system is up-to-date with the latest software releases and security patches.  
## install virtualbox extension
      sudo apt install virtualbox virtualbox-dkms virtualbox-qt virtualbox-ext-pack
# Step2: Install Docker
# Set up Docker's apt repository with the command line below 
       # Add Docker's official GPG key: 
       sudo apt-get update
       sudo apt-get install ca-certificates curl gnupg
       sudo install -m 0755 -d /etc/apt/keyrings
       curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
       sudo chmod a+r /etc/apt/keyrings/docker.gpg


       # Add the repository to Apt sources:
       echo \
       "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
       $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
       sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
       sudo apt-get update
## To install the latest version of Docker packages as of 2023 run:  
        sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
## To confirm if the docker engine is successfully installed run:  
        sudo docker run hello-world
# Step 3: Install minikube
       # Download Minikube and make it executable
       wget https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
       chmod +x minikube-linux-amd64
       sudo mv minikube-linux-amd64 /usr/local/bin/minikube  
## To can verify the version downloaded Run:
       minikube version      

# Step 4:  install Kubectl  
- This is a commandline tool for intereacting with kubernetes cluster
## Run  
      curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
- To make the kubectl binary executable 
# Run
     chmod +x ./kubectl 
- To confirm that the binary file is now in your path 
# Run  
     sudo mv ./kubectl /usr/local/bin/kubectl
# To veryfiy the kubectl you downloaded run:
    kubectl version -o json  --client

