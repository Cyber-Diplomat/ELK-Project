# ELK-Project
Cyber Security's First project 
git clone https://github.com/Cyber-Diplomat## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

**Note**: The following image link needs to be updated. Replace `diagram_filename.png` with the name of your diagram image file.  

  Update the path with the name of your diagram  
  -  ELK-Project/Diagrams/Project Diagram.jpg
  
These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the __ file may be used to install only certain pieces of it, such as Filebeat.

  -  ELK-Project/Diagrams/Project Diagram.jpg
  
This document contains the following details:
- Description of the Topology 
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly ____, in addition to restricting _____ to the network.
-  What aspect of security do load balancers protect? What is the advantage of a jump box?
--  Security aspect of the load balancer is to protect the network from DDoS attack.
--Advantage of a jumpbox is to deliver access to users  form a secure single point      that can be monitored.   

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the logs and system tarffic
-  What does Filebeat watch for?
-  Filebeat watches for log files and locations
-  What does Metricbeat record?
-  Metricbeat collects and records Data to be monitored .

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.
| Name     | Function   | IP Address | Operating System |
|----------|------------|------------|------------------|
| Jump Box | Gateway    | 10.1.0.7   | Linux            |
| ELKVM1   | ELK Server | 10.2.0.4   | Linux            |
| WEB-1    | Web Server | 10.1.0.8   | Linux            |
| WEB-2    | Web Server | 10.1.0.4   | Linux            |
| WEB-3    | Webserver  | 10.1.0.5   | Linux            |

The machines on the internal network are not exposed to the public Internet. 

Only the __ machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- My home public IP

Machines within the network can only be accessed by ---
 Which machine did you allow to access your ELK VM? What was its IP address?
Name of the machine- ElKVM1
Public IP address - 13.90.204.203

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 |       My Home IP  |
| ELKVM1   |  No                 |       10.2.0.4              |            |  Web-1   |  No                   |     10.1.0.8
| Web-2    | No                    |     10.1.0.4                 |
| Web-3    | No                  |    10.1.0.5
### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
-  What is the main advantage of automating configuration with Ansible?_
One of the main advantage of automating configuration with Ansible is -Cloud provisioning
The playbook implements the following tasks:
- In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- Install python-pip
- install docker
- install docker.io
- launch docker elk


The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

**Note**: The following image link needs to be updated. Replace `docker_ps_output.png` with the name of your screenshot image file.  


 Update the path with the name of your screenshot of docker ps output 
 
ELK-Project/Diagrams/ps_docker.jpg 
### Target Machines & Beats
This ELK server is configured to monitor the following machines:
 List the IP addresses of the machines you are monitoring
 
 10.1.0.8
 10.1.0.4
 10.1.0.5

We have installed the following Beats on these machines:
Webservers
Web-1
Web-2
Web-2
-  Specify which Beats you successfully installed_
filebeat and metricbeat (optional) 
These Beats allow us to collect the following information from each machine:
 In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._
- Filebeat- Records  whatever changes occuer in the images of filebeat
- Metricbeat- Records all statistic realted images of the Metricbeat.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the ___ file to etc
- Update the ___ file to include...
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- file -filebeat.yml.new
- copy- /etc/ansible/files/filebeat-configuration.yml
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on? 
- /etc/ansible/host file to add webserver/elkserver ip address
- Which URL do you navigate to in order to check that the ELK server is running?
http://13.90.204.203 :5601/app/kibana

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._