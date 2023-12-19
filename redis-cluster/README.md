## Docker redis cluster

Simple redis cluster for test and development environments.

## Building

```sh
$ docker buildx build --no-cache --platform linux/amd64,linux/arm64  --tag mailtrap/redis-cluster:latest --push .
```

## Using with docker compose

Add to `docker-compose.yml`:

```yaml
version: "3.9"

services:
  redis-cluster:
    image: mailtrap/redis-cluster:latest
    environment:
      CLUSTER_INITIAL_PORT: "6480"
    ports:
      - "6480-6485:6480-6485"
```

Start:

```sh
$ docker-compose up --detach
```

Stop:

```sh
$ docker-compose down --volumes
```
