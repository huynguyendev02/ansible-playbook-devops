Devops tools & platforms installation
=========

Install tools and platform for learning Devops on 3 VMs (both CentOS and Ubuntu), including Gitlab, Docker, GCloud CLI, Jenkins, Nexus, Sonarqube

Requirements
------------

A machine installed with `Virtual Box`. Bootstrapping VMs by `Vagrant`. Refer to this repo to get **Vagrantfile** to use, I follow the exact deployment form that.

You have to install Ansible on the **Controller Node** to use. I have not install in advanced as I want this **Vagrantfile** is as "pure" as possible, only for creating VMs and allowing them to communicate each other. 

My Testing Environment
--------------

| Name | Specs |
| ---- | ----- |
| Virtual Box | Version 7.0.8  |
| Vagrant | Version 2.3.7 |
| Ansible | 2.9 | 
| (Centos7) Node | 1 CPUs, 2048 MB RAM |
| (Ubuntu) Node | 2 CPUs, 2048 MB RAM | 

> Note: Users and password in VM when booting up by Vagrant is 'vagrant' and 'vagrant', this is set up by default.

> You can change system's CPU and RAM above in Vagrantfile; as well as static IP address of each VM and if so, you have to change those in  `host_vars` folder


Playbook information
------------

I defined and mapped each services into each roles. There are 6 roles in total:
- gitlab
- gcpcli
- docker
- jenkins
- nexus
- sonarqube
  
Using variables for future uses. The playbook is compatible for installing in Centos7 and Ubuntu18 (all tested)

Run Playbook
----------------

(Optional) Set `ANSIBLE_CONFIG` to the path of my `ansible.cfg`.

Run the following command on **controller node (Recommend Centos7)**:

```bash
ansible-playbook main.yml -i inventory.ini
```

