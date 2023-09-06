# Ansible

ansible-demo
Ansible Demo

truncate -s 0 access.log ansible --version ansible all -m ping

Controller Machine: Machine where Ansible is installed
Inventory: Information regarding servers to be managed
Playbook: Automation is defined using tasks defined in YAML format
Task: Procedure to be executed
Module: Predefined commands executed directly on remote hosts
Play: Execution of a playbook
Role: a Pre-defined way for organizing playbooks Handlers: Tasks with unique names that will only be executed if notified by another task
Step : 1
yum install ansible

Step :2
ansible --version

Step : 3
Open below file /etc/ansible/ansible.cfg and update content as below

Defaualt Path : config file = /etc/ansible/ansible.cfg
[defaults] host_key_checking = false remote_user = ec2-user ask_pass = false private_key_file = /root/ansible/ec2key.pem roles_path = /root/ansible/roles

[privilege_escalation] become = true become_method = sudo become_user = root become_ask_pass = false

Location where ansible look for hosts
inventory = /etc/ansible/hosts

Step : 4 Update Host File
path : inventory = /etc/ansible/hosts [webapp] 172.12.21.22

Step : 5 Validate Connectivity
ansible all -m ping

Step :6 Create Sample playbook for httpd and run it using below command
ansible-playbook httpdstart.yml

Step 7 : Validate Changes on managed nodes
