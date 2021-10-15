Sonarqube
=========

This ansible role, deploy a sonarqube with postgreSQL over docker containers.

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

#### defaults/main.yml
* **POSTGRES_DOCKER_IMG** is the name of the postgreSQL docker image. By default is **postgres**.
* **CUSTOM_PASSWORD** is the default password of the postgreSQL username.
* **POSTGRES_USERNAME** is the name of the postgreSQL username. By default is **sonarqube**.
* **POSTGRES_DATABASE_NAME** is the name of the postgreSQL database. By default is **sonarqube**.
* **SONARQUBE_DOCKER_IMG** is the name of the Sonarqube docker image. By default is **sonarqube**.

#### vars/main.yml
* **DOCKER_PRUNE** use in case of uninstall sonarqube and pogres. This command delete all containers, images, and volumes. By default is **false**.
* **POSTGRES_DOCKER_TAG**: the tag name of PostgreSQL docker image. By default is **14.0**.
* **SONARQUBE_DOCKER_TAG** the tag name of Sonarqubbe docker image. By default is **8.9.2-community**.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      become: yes
      roles:
         - sonarqube

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
