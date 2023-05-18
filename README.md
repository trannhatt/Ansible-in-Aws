# Project-Ansile-in-Aws

<h6>This is a project to create a server, set up ansible and install and build software via ssh</h6>
<img src="https://webexample75.files.wordpress.com/2023/04/architecture-image.png" height="auto" width="100%" />

## Summary
- To complete this project, I create one EC2 instance as an Ansible machine and three EC2 instances as servers to install the application. I create a key pair on the Ansible machine to establish an SSH connection to the servers.
- Next, I create a security group that allows SSH access. Then, I configure 3 ec2.t2.micro instances using Ansible to install the 'website-demo' Nginx on server-01 and run a Docker container on server-02.  
- To do this, I create an Ansible playbook containing a list of commands called tags that I want to run on the servers.
- Finally, I create an inventory file (hosts) containing the private IP addresses of the EC2 instances that I want to configure and execute the playbook on.
## Set up 
### Prerequisites
- **[Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)** installed.
```properties
sudo apt update
sudo apt install software-properties-common
sudo add-apt-repository --yes --update ppa:ansible/ansible
sudo apt install ansible
``` 
- <i>NOTE: I need install tree in ansible-machine 
</i>

## Running the Configuration

### To create key-pairs on the ansible-machine
  Run the command
```properties
ssh-keygen -t rsa -b 2048
```
 and
```properties
cd .ssh/
cat id_rsa.pub # Then, copy content in .pub and import keypair in aws.
```
### Check the connection to the server with the following command:
  Run the command
```properties
ansible [hosts] -m ping
```  
Or ssh to servers
```properties
ssh [private-ip-ec2]
``` 
 ### To run the playbook we use the following command:
  Run the command
```properties
ansible-playbook [playbook-name]
```
