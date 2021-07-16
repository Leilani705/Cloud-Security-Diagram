# Cloud-Security-Diagram
Description of the Topology
The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.
Load balancing ensures that the application will be highly responsive, in addition to restricting requests to the network.

Load balancers main purpose in the network is to protect traffic by sending requests ony to online servers. The advantage of a jump box is a seperated security zone with controllability. 

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the security and system network.

filebeats watch for data about the file system. 
metric beats collect machine metrics, such as uptime.

The configuration details of each machine may be found below.


ELK server
processing pipeline
10.1.0.4
Operating System



Jump Box
Gateway
10.0.0.1
Linux


Web 1
processing pipeline
10.0.0.8
operating system


Web 2
processing pipeline
10.0.0.5
operating system



Web 3
processing pipeline
10.0.0.7
operating system




Access Policies
The machines on the internal network are not exposed to the public Internet.
Only the jumpBox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:

168.62.196.99

Machines within the network can only be accessed by virtual box.

my personal computer has access to my ELK machine, with the following IP; 73.20.42.8

A summary of the access policies in place can be found in the table below.



elk
yes
73.20.42.8




Jump Box
Yes
10.0.0.8 10.0.0.5 10.0.0.7 10.1.0.4














Elk Configuration
Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because it simplifies tasks.

The main advantage of automating configuration with Ansible is organization and efficiency 

The playbook implements the following tasks:

-log in to jump box provisioner
-switch to root user
-run docker ps -a
-start happy_mcnulty container
-attack happy_mcnulty container

The following screenshot displays the result of running docker ps after successfully configuring the ELK instance.
![dockerps](https://user-images.githubusercontent.com/78867429/124203534-2a093f80-da9a-11eb-9b0f-ded12e806a4e.PNG)




Target Machines & Beats
This ELK server is configured to monitor the following machines:

Elk machine 10.1.0.4

We have installed the following Beats on these machines:

filebeat
metricbeat

These Beats allow us to collect the following information from each machine:

Metric beats allow us to collect machine metrics, such as uptime. Filebeats allow us to collect data about the filesystem.


Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned:
SSH into the control node and follow the steps below:

Copy the playbook.yml file to etc/ansible/roles.
Update the playbook.yml file to include the elk webserver
Run the playbook, and navigate to kibana to check that the installation worked as expected.


The yml files are the playbooks, they're copied in JumpboxProvisioner, in etc/ansible/roles.
update the hosts file to make Ansible run the playbook on a specific machine. Specify which machine to run the elk server on in the host groups by nano.
navigate to the kibana elk url to see that they are running properly.
