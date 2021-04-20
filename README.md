ansible-role-aai-docker-environment
=========

Ansible role for prepare docker environment.

This role will install docker packages and connect to the docker repository, prepare bridge network, create specified volumes and set cron job for auto prune docker images.

Requirements
------------

* community.docker collection is required. Can be installed by `ansible-galaxy collection install community.docker`

Role Variables
--------------

* docker_repository_url - Docker registry URL
* docker_repository_username - Username for connecting to the registry
* docker_repository_password - Password
* docker_network_name - Name of the created docker network
  * The docker network is created in bridge mode
* docker_volumes - List of docker volumes that will be created

Dependencies
------------

* collection `community.docker`

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      vars:
        docker_repository_url: "https://hub.docker.com"
        docker_repository_username: "docker"
        docker_repository_password: "password"
        docker_network_name: "network"
        docker_volumes: []
      roles:
         - { role: ansible-role-aai-docker-environment }


