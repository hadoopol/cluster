# Hadoop cluster on docker

* Summary 
* How it works
* Requirements
* Download the app
* Using the tool
* Todo
* Bugs
* Developer
* Support

### Summary

This is the first attempt to create a hadoop on docker distribution. Named hadoopol cluster. 

On current version, it is able to use docker in one host only, but with HDFS and YARN high availability at container 
level.

### How it works

This app will download zookeeper, hdfs and yarn and create a set of hadoop docker images and proper scripts for initialize
the cluster services on docker.  

### Requirements

To run the installation scripts, it's necessary to have ansible installed ONLY on the machine that will trigger the ansible-playbook command responsible to build/install hadoopol.

Have git installed to be able to clone this repository.

Is necessary to have docker installed on the target server. Target server is the server that will run hadoop on top of docker.

Follow these instructions to install ansible in your machine: https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html

To install docker on the target server follow these instructions: https://docs.docker.com/engine/install/

To install git follow these documentation: https://git-scm.com/book/en/v2/Getting-Started-Installing-Git/

### Download the app

On your OS command line terminal, type below command to clone this repository:

> git clone https://github.com/hadoopol/cluster.git

### Using the app

1. Enter on cloned directory

> cd cluster

2. If needed, edit inventories/development/hosts file and set the server where we are going to install hadoopol.
By default it is set to your localhost

3. If required some customization, using a text editor, edit below files to change cluster settings:
* roles/zookeeper/vars/main.yml
* roles/hdfs-yarn/vars/main.yml


4. run command below to start to deploy the hadoopol cluster on docker:

>ansible-playbook -i inventories/development/hosts hadoop.yml
 
### Todo

A new version, completely refactored is being developed to support n more hosts and make deployment more user friendly. This version is recomended only for 
development purpose.

### Bugs

### Developer

Write to developer @ hadoopol.com and be part of development team.

This app was tested using Ansible version 2.9.10 on top of python 3.8.5

### Support

If you would like commercial support check the list of supporters on supporters.txt file

If you want to provide support services for hadoopol, ask us to include your contact on supporters.txt file








