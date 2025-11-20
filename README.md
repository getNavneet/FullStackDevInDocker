# developement inside docker using docker compose

1. Any command starting with 'docker compose' need to be executed from the directory where compose file is kept or also you can write the file path of compose file like this "docker compose -f /path/to/docker-compose.yml up
".

2. docker compose logs {service_name} - log of particular container, docker compose logs -f {service_name} live log

3. access running container - docker compose exec <service-name> bash

# Server Deployment Instructions

> This method can also be used on the server using Docker Compose.  
> Note: Docker Swarm expects to pull the image from a remote repository.

This codebase has been updated to meet the server deployment requirements.

---

## Steps

1. **SSH into the remote server**  

2. **Add `.env` files** for both frontend and backend:

   - **Backend `.env`:**
     ```env
     FRONTEND_URL=http://3.110.41.179
     ```
     > ⚠️ Make sure there is **no trailing slash (`/`)** after the URL, otherwise it can cause CORS errors.

   - **Frontend `.env`:**
     ```env
     VITE_BACKEND_URL=http://3.110.41.179:8080
     ```

3. **Pull the code from GitHub**  

4. **Build and start containers using Docker Compose**:

   ```bash
   sudo docker compose -f compose.prod.yml up --build -d


