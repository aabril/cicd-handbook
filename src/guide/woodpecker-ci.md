# Woodpecker

> work-in-progress #wip


#### .env file

```env
WOODPECKER_SERVER_DOMAIN=https://woodpecker-subdomain.your-domain.com
WOODPECKER_SERVER_PORT=9000
WOODPECKER_SERVER_GITEA_URL=https://gitea-subdomain.your-domain.com
WOODPECKER_SERVER_GITEA_CLIENT=oauth-client-in-the-format-of---xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
WOODPECKER_SERVER_GITEA_SECRET=oauth-secret-in-the-format-of---xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
WOODPECKER_COMMON_AGENT_SECRET=whatever-long-and-complex-hash-to-connect-agent-and-server
WOODPECKER_SERVER_DOCKER_CONFIG=/home/user/.docker/config.json
WOODPECKER_SERVER_ADMIN=user
```


#### docker-compose.yml

```yaml
# docker-compose.yml
version: '3'

services:
  woodpecker-server:
    image: woodpeckerci/woodpecker-server:latest
    ports:
      - 8000:8000
    volumes:
      # - woodpecker-server-data:/var/lib/woodpecker/
      - ./woodpecker:/var/lib/woodpecker/
    environment:
      - WOODPECKER_OPEN=true
      - WOODPECKER_HOST=${WOODPECKER_SERVER_HOST}
      - WOODPECKER_GITEA=true
      - WOODPECKER_GITEA_URL=${WOODPPECKER_SERVER_GITEA_URL}
      - WOODPECKER_GITEA_CLIENT=${WOODPECKER_SERVER_GITEA_CLIENT}
      - WOODPECKER_GITEA_SECRET=${WOODPECKER_SERVER_GITEA_SECRET}
      - WOODPECKER_AGENT_SECRET=${WOODPECKER_COMMON_AGENT_SECRET}
      - WOODPECKER_DOCKER_CONFIG=${WOODPECKER_SERVER_DOCKER_CONFIG}
      - WOODPECKER_ADMIN=${WOODPECKER_SERVER_ADMIN}

  woodpecker-agent:
    image: woodpeckerci/woodpecker-agent:latest
    command: agent
    restart: always
    depends_on:
      - woodpecker-server
    volumes:
      - /var/run/docker.sock:/var/run/docker.sock
    environment:
      - WOODPECKER_SERVER=woodpecker-server:9000
      - WOODPECKER_AGENT_SECRET=${WOODPECKER_COMMON_AGENT_SECRET}

volumes:
  woodpecker-server-data:
```

And then just run: 
```
docker-compose up --env-file env -d
```




