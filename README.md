# DockerSwarm

**Vagrant** and **Ansible** project to deploy a **Docker Swarm** cluster.
**Docker** and **Docker-Compose** are also installed automatically. 

Architecture of the cluster : 

- master1 *10.0.0.10*
  * worker1 *10.0.0.12*
  * worker2 *10.0.0.13*


Roles : 
- base : installs docker and docker-compose
- swarm-init : initializes a swarm and a token
- node-join : adds the worker nodes to the cluster with the token 
