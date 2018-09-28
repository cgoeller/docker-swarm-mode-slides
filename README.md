# docker-swarm-mode-slides

Introduction to Docker Swarm Mode

Hosted online at: https://cgoeller.github.io/docker-swarm-mode-slides

To create a PDF printout:

1. Open https://cgoeller.github.io/docker-swarm-mode-slides?print-pdf in Chrome
1. Open the in-browser print dialog (CTRL/CMD+P).
1. Change the Destination setting to Save as PDF.
1. Change the Layout to Landscape.
1. Change the Margins to None.
1. Enable the Background graphics option.
1. Click save.

The presentation was created using [reveal.js](http://lab.hakim.se/reveal-js)

## Topics

* a tool for what ? 
* difference to plain docker
* facts: version, release cycle, license
* legacy docker swarm
* similar products - kubernetes, mesos, rancher
* needed knowledge / infrastructure / stuff
* features
  * nodes
  * service
  * task
  * routing mesh
  * load balancing
  * overlay networks
  * service discovery - dns names
  * stacks
  * secrets
  * configs
  * docker compose file
  * healthchecks
  * rolling updates
  * scaling
* under the hood - raft protocol / consensus
* how to setup
  * docker swarm
  * docker node
  * docker stack deploy / ls
  * docker service ls / ps
* cons
  * persistence story
  * host pinning
  * stability / bugs
* example
  * ansible / vagrant generated swarm
* tools
  * portainer
  * traefik
  * commercial docker enterprise
* advice
  * number of master / slave nodes
  * do and don't
* links
   * https://docs.docker.com/engine/swarm/
