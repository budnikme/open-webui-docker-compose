# open-webui-docker-compose

This repository contains a Docker Compose configuration for running OpenWebUI with PostgreSQL + Caddy (reverse proxy and automatic HTTPS) + Watchtower (auto-updates).

##  Prerequisites

- Install Docker - https://docs.docker.com/engine/install/
- Add  `.env` file with configuration (see below)


##  .env file

Create a file named `.env` in the main folder. Fill in your credentials and domain:

```.env
POSTGRES_USER=openwebui
POSTGRES_PASSWORD=supersecurepassword
POSTGRES_DB=openwebui
WEBUI_SECRET_KEY=webuisecretkey
WATCHTOWER_TZ=Europe/Warsaw
WATCHTOWER_CRON=0 0 4 * * *
DOMAIN=your-domain.com
```

## Setup commands

Run these commands from the folder containing `docker-compose.yml`:

- `docker compose up -d` - Start all containers in background
- `docker compose ps` - Check status
- `docker compose logs -f` - Check logs (optional)

After the succesfull setup OpenWebUI will be available at https://your-domain.com/ 