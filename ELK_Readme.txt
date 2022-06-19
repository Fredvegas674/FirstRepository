## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

Diagrams/project1diagram.png

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the beats-playbook.yml file may be used to install only certain pieces of it, such as Filebeat.

  Ansible/beats-playbook.yml

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly stable, in addition to restricting access to the network.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the log files and system statistics.


The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name                | Function  | IP Address | Operating System |
|---------------------|-----------|------------|------------------|
| JumpBox             | Gateway   | 10.0.0.1   | Linux            |
| ELK-Project-elkVm   |           | 10.8.0.4   | Linux            |
| ELK-Project-web1    | Webserver | 10.7.0.5   | Linux            |
| ELK-Project-web2    | Webserver | 10.7.0.4   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
73.171.126.251

Machines within the network can only be accessed by the JumpBox (IP 10.0.0.1)


A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes/No              | 10.0.0.1 10.0.0.2    |
|          |                     |                      |
|          |                     |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because configuration can be automated and repeatable.

The playbook implements the following tasks:
- Install docker
- Install pip3
- Install docker python module

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- ELK-Project-web1 10.7.0.5
- ELK-Project-web2 10.7.0.4

We have installed the following Beats on these machines:
- Filebeat
- Metricbeat

These Beats allow us to collect the following information from each machine:
- Filebeat will collect and centralize log data.
- Metricbeat will monitor the computer usage and services running on the server.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the elk-playbook.yml file to Ansible.
- Update the config file to include the webserver IP addresses
- Run the playbook, and navigate to dvwa.com to check that the installation worked as expected.
