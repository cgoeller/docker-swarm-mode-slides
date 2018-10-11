# Demo

```bash
vagrant up
vagrant ssh docker-1
cd /vagrant/stack
docker stack deploy --compose-file demo.yml demo

```