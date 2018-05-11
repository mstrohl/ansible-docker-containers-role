# docker-containers
An Ansible Docker container role for yum,apt and pip installation with Upstart scripts or systemd services.

It includes container's removal when not defined in the list

## Prerequisites

Ansible >= 2.2

python >= 2.6

docker-py >= 1.7.0

Docker API >= 1.20


## Usage

Include the folder in your roles directory. You can edit the configuration in, for example, your group_vars, like this:

```
docker_containers:
  - name: hello-world
    image: nginx
    published_ports: 
      - 1280:80
      - 1245:443
    volumes:
      - /home/user:/tmp
      - /var/tmp:/var/tmp
    env:
      HELLO: WORLD
      USER: PASSWORD
```

## Parameters

Parameters are some of ansible's module docker_container parameters that fit my needs(http://docs.ansible.com/ansible/latest/modules/docker_network_module.html)

```
#global params
playbook_debug: 
enable_remove_unwanted_containers:
enable_remove_unwanted_containers_img:  
# container definition 
  - name: 
    image: 
    ignore_image: 
    pull: 
    state: 
    cpu_period: 
    cpu_quota: 
    cpu_shares: 
    memory: 
    memory_reservation: 
    memory_swappiness: 
    memory_swap: 
    recreate: 
    restart_policy: 
    links: 
    network_mode: 
    networks: 
    detach: 
    volumes: 
    published_ports: 
    ulimits: 
    env: 
    env_file: 
    log_driver: 
    command:
```

## Author

STROHL Matthieu <postmaster@smartdeploy.io>

## License

MIT
