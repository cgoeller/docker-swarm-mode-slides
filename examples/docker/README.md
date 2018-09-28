# Docker example

This example contains two vagrant environments, which can be found in the folders:

* `singlevm`
* `swarm`

## Single VM

Creates a VMm, installs the Docker engine using Ansible

```bash
vagrant up
# Login
vagrant ssh
```

## Swarm

Creates 3 VMs and configures docker swarm mode using Ansible, which is executed on an additional controller VM.

VMs: docker-1, docker-2, docker-3 with host-only networking at 192.168.56.11, 192.168.56.12, 192.168.56.13
The controller VM has the IP 192.168.56.10. It is the primary machine in Vagrant.

The docker swarm will be populated with the services: docker registry, portainer, traefik.

Registry: http://192.168.56.11:5000/v2/_catalog/
Portainer: http://192.168.56.11:9000/
Trafik: http://192.168.56.11:8080/

### Startup

```bash
vagrant up

# Login to controller
vagrant ssh

# Login to docker-1
vagrant ssh docker-1
```

To install an Elasticsearch cluster:

```bash
vagrant provision --provision-with setup_es

# Access ES using:

# Over traefic
curl -vs -u "user:password" -H "Host: es.test.local" http://192.168.56.11/

# Over nginx
curl -vs http://192.168.56.11:90/

# Over jwilder/nginx-proxy
curl -vs -H "Host: es.test.local" http://192.168.56.11:100/

# Over port binding
curl -vs http://192.168.56.11:9200/
```

Optionally add the following line to your `/etc/hosts` to access ES by hostname.

```none
192.168.56.11 es.test.local
```
