ansible-role-aai-docker-environment
=========

Ansible role for prepare docker environment.

This role will install docker packages and connect to the docker repository, prepare bridge network, create specified volumes and set cron job for auto prune docker images.

Requirements
------------

* community.docker collection is required. Can be installed by `ansible-galaxy collection install community.docker`

Role Variables
--------------

* docker_repositories - Definition of docker repositories to login
* docker_network_name - Name of the created docker network
  * The docker network is created in bridge mode
* docker_volumes - List of docker volumes that will be created

Dependencies
------------

* collection `community.docker`

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:
```yaml
    - hosts: servers
      vars:
        docker_repositories:
          - { url: "Repository URL", username: "username", password: "password" }
        docker_network_name: "network"
        docker_volumes: []
      roles:
         - { role: ansible-role-aai-docker-environment }
```

