# developement inside docker using docker compose

1. Any command starting with 'docker compose' need to be executed from the directory where compose file is kept or also you can write the file path of compose file like this "docker compose -f /path/to/docker-compose.yml up
".

2. docker compose logs {service_name} - log of particular container, docker compose logs -f {service_name} live log

3. access running container - docker compose exec <service-name> bash

# this method can also we used on the server using docker compose but docker swarm expect to pull image from remote directory