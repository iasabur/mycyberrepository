# mycyberrepository
cybersecurity boot camp repository
ELK deployment README
The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.
Load balancing ensures that the application will be highly available, in addition to restricting access to the network.
A gateway makes a network more secure by providing an extra layer of security
Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the _____ and system files.
Filebeat watches for changes in system files
Metricbeat records system and service metrics
The configuration details of each machine may be found below. Note: Use the Markdown Table Generator to add/remove values from the table.
Name
Function
IP Address
Operating System
Jump Box
Gateway
  10.0.0.8
         Linux
Web-1
expose DVWA
10.0.0.9
          Linux
Web-2
expose DVWA
10.0.0.10
          Linux
Web-3

ELK Server           monitor VM’s for changes to 
expose DVWA
   10.0.0.11
           Linux



Access Policies
The machines on the internal network are not exposed to the public Internet.
Only the ELK machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
17.118.195.17
Machines within the network can only be accessed by _____.
Jump-Box (75.118.195.17)
A summary of the access policies in place can be found in the table below.
Name
Publicly Accessible
Allowed IP Addresses






Jump Box 
No 
75.118.195.17


Web-1
Web-2 No   
Web-3 No
ElkServ Y 
No
75.118.195.17
75.118.195.17
75.118.195.17
75.118.195.17
Elk Configuration
Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
It eliminates the possibility of human error.
The playbook implements the following tasks:
Set the vm.max_map_count to 262144
Installs the following apt packages:


docker.io: The Docker engine, used for running containers.
python3-pip: Package used to install Python software.
Installs the following pip packages:


docker: Python client for Docker. Required by Ansbile to control the state of Docker containers.
Downloads the Docker container called sebp/elk:761. sebp is the organization that made the container. elk is the container and 761 is the version.


Configures the container to start with the following port mappings:


5601:5601
9200:9200
5044:5044

Starts the container.

The following screenshot displays the result of running docker ps after successfully configuring the ELK instance.

Target Machines & Beats
This ELK server is configured to monitor the following machines:
10.0.0.9
10.0.0.10
10.0.0.11
We have installed the following Beats on these machines:
filebeat
These Beats allow us to collect the following information from each machine:
Filebeat collects file logs which tells us when and which files have changed.
Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned:
SSH into the control node and follow the steps below:
Copy the hosts file to /etc/ansible/hosts.
Update the hosts file to include new ip.
Run the playbook, and navigate to vm’s to check that the installation worked as expected.
TODO: Answer the following questions to fill in the blanks:
Which file is the playbook? Filebeat.yml Where do you copy it? /etc/filebeat
Which file do you update to make Ansible run the playbook on a specific machine? Hosts How do I specify which machine to install the ELK server on versus which to install Filebeat on? Install elk server under ‘elk’ heading in hosts file, filebeat under ‘webservers.
_Which URL do you navigate to in order to check that the ELK server is running? http://13.83.80.140:5601/app/kibana
