## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![TODO: Update the path with the name of your diagram](Images/diagram_filename.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

 

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly __functional and available___, in addition to restricting __traffic___ to the network.
- _TODO: What aspect of security do load balancers protect? 
  -  Load balancers add resiliency by rerouting live traffic from one server to another if a server falls prey to a DDoS attack or otherwise becomes unavailable.
- What is the advantage of a jump box?_
  - A Jump Box Provisioner is also important as it prevents Azure VMs from being exposed via a public IP Address. This allows us to do monitoring and logging on a single box. We can also restrict the IP addresses able to communicate with the Jump Box, as we've done here.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the _____ and system _____.
- _TODO: What does Filebeat watch for?_
  -Filebeat monitors the log files or locations that you specify, collects log events, and forwards them either to Elasticsearch or Logstash for indexing.
  
- _TODO: What does Metricbeat record?_
  -Metricbeat takes the metrics and statistics that it collects and ships them to the output that you specify, such as Elasticsearch or Logstash.
  
The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.
Workstation and Jump-Box-Provisioner through SSH Jump-Box.
| Name      | Function     | IP Address               | Operating System |
|-----------|--------------|--------------------------|------------------|
| Jump Box  | Gateway      | 10.1.0.4 / 20.85.232.66  | Linux            |
| Web-1     | UbuntuServer | 10.1.0.5 / 40.114.124.38 | Linux            |
| Web-2     | UbuntuServer | 10.1.0.6 / 40.114.124.38 | Linux            |
| DVWA-VM3  | UbuntuServer | 10.1.0.7 / 40.114.124.38 | Linux            |
| ELKserver | UbuntuServer | 10.2.0.4 / 20.84.136.248 | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the _Jump-Box-Provisioner____ machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
  Workstation MY Public IP through TCP 5601.

Machines within the network can only be accessed by __Workstation and Jump-Box-Provisioner through SSH Jump-Box.___.
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address?_
  -  Jump-Box-Provisioner IP : 10.1.0.4 via SSH port 22

A summary of the access policies in place can be found in the table below.

| Name      | Publicly Accessible | Allowed IP Addresses                    |
|-----------|---------------------|-----------------------------------------|
| Jump Box  | Yes                 | 20.85.232.66 (Workstation IP on SSH 22) |
| Web-1     | No                  | 10.1.0.4 on SSH 22                      |
| Web-2     | No                  | 10.1.0.4 on SSH 22                      |
| DVWA-VM3  | No                  | 10.1.0.4 on SSH 22                      |
| ELKserver | No                  | Workstation MY Public IP using TCP 5601 |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible?_
  - Ther are multiple advantages, Ansible lets you quickly and easily deploy multitier applications throug a YAML playbook.
    You don't need to write custom code to automate your systems.
      Ansible will also figure out how to get your systems to the state you want them to be in.

The playbook implements the following tasks:
  -Specify a different group of machines:
 
  -Install Docker.io
  
  -Install Python-pip
  
  -Use pip module (It will default to pip3)

  -Increase Virtual Memory
 
  -Download and Launch ELK Docker Container (image sebp/elk)



The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._

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

