docker-client-debian
====================

Based off of martinsthiago/docker-client; with Debian as the base image instead of Ubuntu.

Run a docker client within docker!

Download
--------

```
# pull the image
docker pull unenglishable/docker-client-debian
# (optional) tag the image
docker tag unenglishable/docker-client-debian docker-client-debian
```

Use as a base image
-------------------

Dockerfile
```
FROM unenglishable/docker-client-debian

...
```

Client server version mismatch
------------------------------

Fix client/server version mismatches by setting `DOCKER_API_VERSION`
environment variable.


```
DOCKER_API_VERSION=$(docker version --format="{{ .Server.ApiVersion }}")

docker run -it -e DOCKER_API_VERSION=$DOCKER_API_VERSION -v /var/run/docker.sock:/var/run/docker.sock docker-client-debian
```
