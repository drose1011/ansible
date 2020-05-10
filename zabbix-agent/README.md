This ansible script is used to install zabbix-agent on Ubuntu 16 and 18, Centos 7 and Windows machine.

You can create a new inventory file in the same directory. Here I used the default inventory in /etc/ansible/hosts. The install_zabbix_agent.yml file can install zabbix-agent in linux machines while for windows there is a separate file called windows.yml.

The variables are defined in group_vars directory. Common variables for linux is defined undedr the file all.yml while for windows machine, windows.yml fileis used.

Prerequisite for windows: Copy and run the windowsremoteansible.ps1 powershell script in windows machine before running the ansible script. In Windows environment, winrm is used as an alternative SSH for connecting to windows machine. This powershell script allows the host to listen to winrm request.

Run the command : ansible-playbook install_zabbix_agent.yml --ask-become-pass   #For linux machine

Run the command: ansible-playbook windows.yml   #For windows machine

For windows machine I have set the username and password in the group_vars/windows.yml which is encrypted using ansible vault.