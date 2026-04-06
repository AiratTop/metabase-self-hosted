# AGENTS.md

## Purpose
Public self-hosted deployment template for Metabase BI with PostgreSQL metadata DB.

## Repository Role
- Category: `*-self-hosted` (public GitHub repository).
- Related local stack: `../metabase-docker`.
- Main entrypoint: `docker-compose.yml`.

## Stack Summary
- Services: `metabase`, `metabase-psql`.
- Exposed port: `3000`.
- External network: `shared_network`.

## Data and Config
- PostgreSQL data: `./data/metabase-psql`.
- Logging override: `./metabase-log4j2.xml` mounted into Metabase.

## Operations
- Restart stack: `./restart-docker.sh`.
- Update images and restart: `./update-docker.sh`.
- Backup helper: `./backup.sh`.

## AI Working Notes
- Keep `MB_DB_*` settings aligned with `metabase-psql` service.
- Keep `PSQL_PWD` and other credentials in `.env`, not in committed files.
- Preserve `depends_on` health condition for reliable startup.
