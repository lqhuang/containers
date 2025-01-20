# containers

lqhuang's tech stacks in container way

## Why

Serveral main stream container images are not good enough for fast prototyping and local dev & testing. In my humble opinions:

- Docker official image may not the best choice for local dev. For example: My most frequently used image [postgres](https://hub.docker.com/_/postgres) is
  1. Run as root user (it's not a big deal but not good)
  2. No SSL by default
  3. Missing some useful extensions (eg: `pgvector`)
- On the other sides, bitnami container images are good and developer oriented. But they are a bit of over engineering and introduce extra configuration burdens (eg: all data folders are layouted under `/bitnami/xxx`)

And I want to make a collections of lightweight and developer friendly container images for my own frequently used teck stacks.

Goals

- lightweight but full features
  - lightwight is still first priority
- rootless friendly
  - prefer no root user
  - assign a target user or align to real user easily
- security
  - prefer SSL by default
  - optional mTLS
- Optimize for compose stack
- Optimize for [devcontainers](https://containers.dev/)

## Credits

- [bitnami/containers](https://github.com/bitnami/containers): Bitnami container images <https://bitnami.com>
- [docker/awesome-compose](https://github.com/docker/awesome-compose): Awesome Docker Compose samples <https://docs.docker.com/compose/>
- [docker-library/official-images](https://github.com/docker-library/official-images): Primary source of truth for the Docker "Official Images" program <https://hub.docker.com/u/library>
- [docker-library/postgres](https://github.com/docker-library/postgres): Docker Official Image packaging for Postgres <http://www.postgresql.org>
