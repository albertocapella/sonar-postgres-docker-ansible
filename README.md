Ansible Sonarqube PostgreSQL
=========
This playbook install docker and deploy Sonarqube using PostgreSQL with JDBC over Amazon Linux

Requirements
------------

Software for bastion host:
* [ansible](https://www.ansible.com/) 2.9.26. An extra-simple tool/framework/API for doing 'remote things'.  It is the simplest way to automate apps and IT infrastructure.  Application Deployment + Configuration Management + Continuous Delivery.
> The bastion host will execute this playbook

Software for remote host:
* OpenSSH Server.
* Docker API >= 1.20
* Docker SDK for Python
> Read more information [here](https://docs.ansible.com/ansible/2.9/modules/docker_container_module.html).

AWS EC2 instance or a bare metal server with the following requirements:
* At least 1GB of RAM.
* At least 10GB of storage.

Role Variables
--------------

#### external_vars.yml
* **DOCKER_PRUNE** use in case of uninstall sonarqube and pogres. This command delete all containers, images, and volumes. By default is **false**.

Dependencies
------------

* [docker](roles/docker/README.md)
* [sonarqube](roles/sonarqube/README.md)

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      become: yes
      roles:
         - docker
         - sonarqube
