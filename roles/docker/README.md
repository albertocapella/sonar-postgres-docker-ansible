docker
=========

This role install docker over Amazon Linux.

Requirements
------------

Software for bastion host:
* [ansible](https://www.ansible.com/) 2.9.26. An extra-simple tool/framework/API for doing 'remote things'.  It is the simplest way to automate apps and IT infrastructure.  Application Deployment + Configuration Management + Continuous Delivery.
> The bastion host will execute this playbook

Software for remote host:
* OpenSSH Server.
> Read more information [here](https://docs.ansible.com/ansible/2.9/modules/docker_container_module.html).

AWS EC2 instance or a bare metal server with the following requirements:
* At least 1GB of RAM.
* At least 10GB of storage.

Role Variables
--------------

#### defaults/main.yml
* **CONF_MIRROR**, is used to setup docker mirror, can be true or false. By default is **true**.

#### vars/main.yml
* **AMZ_DOCKER_REQUIREMENTS**, a list of packages needed to install docker.
* **AMZ_DOCKER_PACKAGES**, a docker package name to will be install.

Dependencies
------------

* [docker](../docker/README.md)

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      become: yes
      roles:
         - docker
