# IDP_auxiliary
Auxiliary tools and configurations

# Kong
* Must create kong-net network using `docker network create --driver overlay --scope swarm kong-net`
* Add to the swarm before the microservices. Do that with `docker stack deploy -c docker-compose.yml kong_stack`
* To access the auth service, send requests to localhost:8000/auth instead of localhost:3001.