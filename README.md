# AWS-Ansible
#Ansible
sudo apt-get update
sudo apt install software-properties-common
sudo apt-add-repository ppa:ansible/ansible
sudo apt update sudo apt install ansible

#on hosts
sudo apt-get update
sudo apt-get install python

#on master
ssh-keygen

#on slave
hosti ansible_ssh_host-203.0.113.1

#Print "Hello World from SJSU"
mkdir playbooks
cd playbooks
 
---
- name: This is a hello-world example
  hosts: all
  tasks:
    - name: Create a file called '/tmp/testfile.txt' with the content 'hello world from SJSU'.
      copy:
        content: Hello world from SJSU
        dest: /tmp/testfile.txt'
        
#deploy and undeploy web servers in aws ansible playbooks
---
- name: installing httpd package
  package:
     name: "httpd"
     state: present
-name: Create a file
 copy:
    dest: "{{index path}}"
    content:
       Hello World from SJSU
-name: Web services
 service:
    name: "httpd"
    state: started


- hosts: all
  remote_user: ec2-user 
  roles:      
    - undeploy-web 
