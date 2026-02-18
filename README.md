# Docker Commands for DevOps Engineers

---

 Docker Commands Every DevOps Engineer Should Know

Most people think Docker is just:

```
docker run <image_name>
```

---

 **BASIC COMMANDS**

| Command                                  | What it does                                   |
| ---------------------------------------- | ---------------------------------------------- |
| `docker --version`                     | Check installed version                        |
| `docker info`                          | System-level info (storage, swarm, containers) |
| `docker pull <image>`                  | Download image from registry                   |
| `docker run -it -d -p 8080:80 <image>` | Create & start container                       |
| `docker ps`                            | List running containers                        |
| `docker ps -a`                         | List all containers                            |
| `docker stop / start / restart <id>`   | Manage container state                         |
| `docker rm <id>`                       | Remove container                               |
| `docker rmi <id>`                      | Remove image                                   |
| `docker exec -it <id> /bin/bash`       | Shell inside container                         |
| `docker logs <id>`                     | View container logs                            |
| `docker inspect <id>`                  | Full JSON metadata                             |

---

**IMAGE MANAGEMENT**

| Command                             | What it does                |
| ----------------------------------- | --------------------------- |
| `docker build -t <name> .`        | Build image from Dockerfile |
| `docker tag <image> <repo>:<tag>` | Version your image          |
| `docker push <repo>:<tag>`        | Push to Docker Hub / ECR    |
| `docker history <image>`          | View image layers           |

---

**VOLUMES** (Data Persistence)

| Command                          | What it does              |
| -------------------------------- | ------------------------- |
| `docker volume create <name>`  | Create persistent storage |
| `docker volume ls`             | List all volumes          |
| `docker volume inspect <name>` | Volume details            |
| `docker volume rm <name>`      | Remove volume             |
| `docker volume prune`          | Remove all unused volumes |

---

**NETWORKING**

| Command                           | What it does           |
| --------------------------------- | ---------------------- |
| `docker network ls`             | List networks          |
| `docker network create <name>`  | Create custom network  |
| `docker network inspect <name>` | Check IPs, subnets     |
| `docker network rm <name>`      | Remove network         |
| `docker network prune`          | Remove unused networks |

---

**DOCKER COMPOSE** (Multi-Container Apps)

| Command                  | What it does         |
| ------------------------ | -------------------- |
| `docker compose up -d` | Start all services   |
| `docker compose down`  | Stop & remove all    |
| `docker compose build` | Build all images     |
| `docker compose ps`    | Status of services   |
| `docker compose logs`  | Logs of all services |

---

**DOCKER SWARM**

| Command                             | What it does             |
| ----------------------------------- | ------------------------ |
| `docker swarm init`               | Initialize swarm manager |
| `docker swarm join-token worker`  | Get worker join token    |
| `docker swarm join-token manager` | Get manager join token   |
| `docker node ls`                  | List all nodes           |
| `docker node inspect <id>`        | Node details             |

---

**DOCKER SERVICES**

| Command                                         | What it does        |
| ----------------------------------------------- | ------------------- |
| `docker service create --name <name> <image>` | Create a service    |
| `docker service ls`                           | List services       |
| `docker service ps <name>`                    | Tasks of a service  |
| `docker service scale <name>=5`               | Scale to 5 replicas |
| `docker service update <name>`                | Update a service    |
| `docker service rm <name>`                    | Remove a service    |

---

**DOCKER STACK**

| Command                                       | What it does      |
| --------------------------------------------- | ----------------- |
| `docker stack deploy -c <file.yml> <stack>` | Deploy a stack    |
| `docker stack ls`                           | List stacks       |
| `docker stack services <stack>`             | Services in stack |
| `docker stack ps <stack>`                   | Tasks in stack    |
| `docker stack rm <stack>`                   | Remove stack      |

---

**CLEANUP** (Production Must-Know)

| Command                    | What it does              |
| -------------------------- | ------------------------- |
| `docker system prune -a` | Remove everything unused  |
| `docker container prune` | Remove stopped containers |
| `docker image prune`     | Remove dangling images    |
| `docker builder prune`   | Clear build cache         |

>  Never run prune in production without checking first!

---

**Real-World Flow (How it actually works in production)**

```
Developer pushes code
       ↓
Jenkins pipeline triggers
       ↓
docker build creates image
       ↓
Image pushed to AWS ECR
       ↓
Kubernetes deploys the new image
```

---
