# containers

lqhuang's tech stacks in container way

## Why

Serveral main stream container images are not good enough for fast prototyping and local dev & testing. In my humble opinions:

- Docker official image may not the best choice for local dev. For example: My most frequently used image [postgres](https://hub.docker.com/_/postgres) is
  1. run as root user (it's not a big deal but bad practice and annoying for some cases)
  2. no TLS by default
  3. missing some useful extensions (eg: `pgvector`)
- On the other sides, bitnami container images are good and developer oriented. But they are a bit of over engineering and introduce extra configuration burdens (eg: all data folders are layouted under `/bitnami/xxx`)

And I want to make a collections of lightweight and developer friendly container images for my own frequently used teck stacks.

Goals

- lightweight but full features
  - lightwight is still first priority
- rootless friendly
  - prefer no root user
  - assign a target user or align to real user easily
- security (yes, in local env)
  - prefer TLS by default
  - disable no-password accessing
  - (optional) mTLS
- maintainable
- optimize for compose stack
- (optional) optimize for [devcontainers](https://containers.dev/)

NON-Goals

- production ready
- smallest size as possible

## Credits

- [bitnami/containers](https://github.com/bitnami/containers): Bitnami container images <https://bitnami.com>
- [docker/awesome-compose](https://github.com/docker/awesome-compose): Awesome Docker Compose samples <https://docs.docker.com/compose/>
- [docker-library/official-images](https://github.com/docker-library/official-images): Primary source of truth for the Docker "Official Images" program <https://hub.docker.com/u/library>
- [docker-library/postgres](https://github.com/docker-library/postgres): Docker Official Image packaging for Postgres <http://www.postgresql.org>
- [clearlinux/dockerfiles](https://github.com/clearlinux/dockerfiles): Clear Linux-based Docker containers
- [slimtoolkit/slim](https://github.com/slimtoolkit/slim): Slim(toolkit): Don't change anything in your container image and minify it by up to 30x (and for compiled languages even more) making it secure too! (free and open source)
