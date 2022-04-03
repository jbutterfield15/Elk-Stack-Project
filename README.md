## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![TODO: Update the path with the name of your diagram](Images/diagram_filename.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

  - _TODO: Enter the playbook file._

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available and secure, in addition to restricting access to the network.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the log events and system metrics.

The configuration details of each machine may be found below.

| Name     | Function | IP Address    |	OS      |
|----------|----------|---------------|---------|
| Jump Box | Gateway  | 104.43.143.50 |Linux    |
| WEB-1-VM | Server   | 10.0.0.7      |Linux    |
| WEB-2-VM | Server   | 10.0.0.8      |Linux    |
| ELK      | Server   | 10.1.0.4      |Linux    |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump Box and Elk machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- 24.7.243.165

Machines within the network can only be accessed by the Jump Box Provisioner and it's IP address is 10.0.0.4

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses  |
|----------|---------------------|-----------------------|
| Jump Box | Yes                 |104.43.143.50          |
| Web-1-VM | No                  |10.0.0.7               |
| Web-2-VM | No                  |10.0.0.8               |
| Elk      | Yes                 |20.230.176.40, 10.1.0.4|

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible?_

The playbook implements the following tasks:
- Increases Virtual Memory
- Installs services such as docker.io and python3-pip
- Enables docker service on boot

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

https://github.com/jbutterfield15/Elk-Stack-Project/blob/main/Images/Elk%20Server%20docker%20ps.PNG

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- Web-1-VM - 10.0.0.7
- Web-2-VM - 10.0.0.8

We have installed the following Beats on these machines:
- Metricbeat
- Filebeat

These Beats allow us to collect the following information from each machine:
- Metricbeat allows us to collect more statistical data where as Filebeat allows us to collect various log event data. 

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the playbook (.yml) file to the /etc/ansible/ directory
- Update the /etc/ansible/hosts file to include the webservers and elk machine IP addresses
- Run the playbook, and navigate to Kibana to check that the installation worked as expected
