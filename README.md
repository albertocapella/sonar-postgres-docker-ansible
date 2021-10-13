docker
=========

This role install docker and deploy sonarqube with postgreSQL over Amazon Linux or Ubuntu.

Requirements
------------

Hardware:
* At least 1GB of RAM.
* At least 10GB of storage.

Role Variables
--------------

#### defaults/main.yml
* **CONF_MIRROR**, can be true or false, and is used to setup (or not) the custom mirror used to install docker.

#### vars/main.yml
* **DOCKER_PREREQUISITES**, a list of the packages needed to install docker.
* **DOCKER_PACKAGES**, a list of the docker packages to will be install.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      become: yes
      roles:
         - docker

> By default, this role not configure apt repository, to configure it, set CONF_MIRROR to true.
