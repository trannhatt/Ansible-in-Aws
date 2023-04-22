# Project-Ansile-in-Aws

<h6>This is a project to create a server, set up ansible and install and build software via ssh</h6>
<img src="https://webexample75.files.wordpress.com/2023/04/architecture-image.png" height="auto" width="100%" />

## Summary
- 1 ec2.t2.micro use as ansible-machine, 3 ec2.t2.micro use as server to deploy the application.
- I will create keypair on ansible-machine and use the keypair establish ssh connection to server.
- reate security group that allows ssh access.
- 3 ec2.t2.micro will configure with ansible and install website-demo nginx in server-01, install docker \& run container in server-02.
- I will create ansible playbook a playbook contains a list of commands called tags that I want to run on the servers.
- Next, I will also create an inventory file (hosts) contains private ip address of ec2 I want to configure and execute playbook.
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
