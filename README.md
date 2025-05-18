# IDP_auxiliary: auxiliary tools and configurations

## Docker Swarm
* In Docker use `docker swarm init` before any other command

## Kong
* Must create kong-net network using `docker network create --driver overlay --scope swarm kong-net`
* Add to the swarm before the microservices. Do that with `docker stack deploy -c docker-compose.yml kong_stack`
* To access the auth service, send requests to localhost:8000/auth instead of localhost:3001
* 
## Portainer
* Must create kong-net network using `docker network create --driver overlay --scope swarm kong-net`
* Add to the swarm before the microservices. Do that with `docker stack deploy -c docker-compose.yml portainer_stack`
* Open http://localhost:8000/portainer to access the web platform for portainer.io (enter the username and password for the admin); Portainer is integrated in Kong service now so we replaced localhost:9000 with the right configuration

## Monitoring
* Must create kong-net network using `docker network create --driver overlay --scope swarm kong-net`
* Then add to the swarm: `docker stack deploy -c prometheus-stack.yml monitoring_stack`
* To access prometheus : `localhost:9090`
* To access grafana: `localhost:3017`