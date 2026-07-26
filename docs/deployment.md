---
title: Deployment
audience: technical
last_reviewed: 2026-07-26
---

# Deployment

AGM runs Zammad from the official
[`zammad/zammad-docker-compose`](https://github.com/zammad/zammad-docker-compose)
stack (image: `ghcr.io/zammad/zammad`), not by building this repository
directly — this repo is a source mirror kept for reference and future
build/CI needs, not the deployed artifact.

## Current instance

- **URL:** [https://zammad.agmegypt.com](https://zammad.agmegypt.com)
- **Lifecycle:** production
- **Previously:** ran on the now-decommissioned AGM Server 130
  (E:\zammad, port 8083); migrated off that host in 2026-07.

## Stack

Standard `zammad-docker-compose` container set: nginx, railsserver,
websocket, scheduler, postgresql, redis, memcached, elasticsearch, backup,
init.

## Configuration notes carried over from the previous deployment

- **CSRF / reverse proxy:** `NGINX_SERVER_SCHEME=https` must be set in the
  stack's `.env`. Without it, the internal nginx forwards
  `X-Forwarded-Proto: http`, which breaks `Secure` session cookies behind
  an HTTPS-terminating reverse proxy.
- **Timezone / locale:** `TZ=Africa/Cairo`, `Setting.locale_default=en-gb`
  (DD/MM/YYYY), `Setting.timezone_default=Africa/Cairo`. The Docker image
  default `TZ` is `Europe/Berlin` — the override must live in `.env` (not
  `docker-compose.yml`) so it survives `git pull` on the compose repo.
- **Admin account:** `dto@aboughalymotors.com` (DTO AGM).

## Related

- [3CX Integration](3cx-integration.md)
- [zammad-docker-compose](https://github.com/zammad/zammad-docker-compose)
