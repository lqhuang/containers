# Init like `initContainers`

In Kubernetes, an [init container](https://kubernetes.io/docs/concepts/workloads/pods/init-containers/) is a container that starts and must complete successfully before the primary container can start.

```yaml
services:
  db:
    image: postgres-distroless
    user: postgres
    volumes:
      - pgdata:/var/lib/postgresql/data/
    depends_on:
      db-init:
        condition: service_completed_successfully

  db-init:
    image: postgres:alpine3.18
    environment:
      POSTGRES_PASSWORD: example
    volumes:
      - pgdata:/var/lib/postgresql/data/
    user: postgres
    command: docker-ensure-initdb.sh

volumes:
  pgdata:
```
