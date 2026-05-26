# Maintenance Page

A lightweight static maintenance page served via nginx in Docker.

## Stack

- **nginx:alpine** — static file server
- **Docker Compose** — container management

## Files

| File | Purpose |
|---|---|
| `index.html` | Maintenance page UI |
| `nginx.conf` | nginx config with rate limiting and security headers |
| `docker-compose.yml` | Container definition, exposes port `3002` |

## Usage

```bash
docker compose up -d
```

Page is available at `http://localhost:3002`.

## nginx

- Rate limit: 10 req/s per IP, burst 20
- Security headers: `X-Frame-Options`, `X-Content-Type-Options`
- All routes serve `index.html`

## Stop

```bash
docker compose down
```
