# Docker NUXT.js

This image is based on node alpine. It build's and run's a NUXT application in production mode.

## Usage

 In your NUXT project add the following to your `Dockerfile`:

```
FROM bosenok/nuxt
```

OR

```
FROM bosenok/nuxt:build-essentials
```

## Image on Docker Hub

https://hub.docker.com/r/bosenok/nuxt/

## Build and push all images

```bash
docker image build -t nuxt . && \

docker tag nuxt bosenok/nuxt && \

docker push bosenok/nuxt && \


cd build-essentials/ && \

docker image build -t nuxt:build-essentials . && \

docker image tag nuxt:build-essentials bosenok/nuxt:build-essentials && \

docker push bosenok/nuxt:build-essentials && \

cd ..
```
## License

MIT
