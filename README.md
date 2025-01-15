# Getting started with Strapi

## Build the images

### Developpement

```
podman build . -f Dockerfile -t strapi-dev
```

### Production

```
podman build \
  --build-arg NODE_ENV=production \
  -t strapi-prod:latest \
  -f Dockerfile.prod .
```

## Start the containers

```
podman run --rm \
    -p 1337:1337 \
    --env-file .env \
    -v tmp-strapi:/opt/app/.tmp:Z \
    -v uploads-strapi:/opt/app/public/uploads:Z \
    localhost/strapi-dev:latest
```
