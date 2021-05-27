## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

[Network Diagram](Images/Project1.png)

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

Load balancing ensures that the application will be highly available, in addition to restricting access to the network.
- Load balancers protect against DoS attacks
- _TODO: The advantage of the jump box is ...

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the Data and system logs.
- Filebeat monitors the log files or locations that you specify, collects log events such as;
 	syslog updates
	sudo commands
	ssh logins
	changes to user accounts
- Metricbeat monitors metrics and statics of target mahines such as;
	CPU
	Memory
	Disk Space

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name                | Function   | IP Address             | Operating System |
|---------------------|------------|------------------------|------------------|
| Jum-Box-Provisioner | Jump Box   | 20.83.226.108/10.0.0.4 | Ubuntu           |
| Web-1               | Web Server | 52.151.21.43/10.0.0.5  | Ubuntu           |
| Web-2               | Web Server | 52.151.21.43/10.0.0.6  | Ubuntu           |
| ELK-Server-RT005    | ELK Server | 104.209.145/10.1.0.5   | Ubuntu           |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jum-Box-Provisioner machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- 119.18.1.64

Machines within the network can only be accessed by the Ansible container running on the Jum-Box-Provisioner.
- Jum-Box-Provisioner
- 10.0.0.4

A summary of the access policies in place can be found in the table below.

| Name                | Publicly Accessible | Allowed IP Addresses |
|---------------------|---------------------|----------------------|
| Jum-Box-Provisioner | Yes                 | 119.18.1.64          |
| Web-1               | Yes                 | 119.18.1.64          |
| Web-2               | Yes                 | 119.18.1.64          |
| ELK-Server-RT005    | Yes                 | 119.18.1.64          |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because it allows for fast, repeatable and error free provisioning of the VM's

The playbook implements the following tasks:
- Install Docker
- Install required Python packages
- Set the VM memory parameter max_map_count
- Download and launch the Elk container
- Enable the docker to run on startup

The following googledoc has the screenshot that displays the result of running `docker ps` after successfully configuring the ELK instance.

[docker ps output](Images/docker_ps.PNG)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- 10.0.0.5
- 10.0.0.6 

We have installed the following Beats on these machines:
- Syslog
- Sudo commands
- SSH logins
- New Users and groups

These Beats allow us to collect the following information from each machine:
- Syslog events, sudo executions, ssh login attempts and user creations and changes.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the _____ file to include...
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._