## Building the Docker Container

```shell script
docker build -t sa-webapp .
```

## Running the Docker Container

```shell script
docker run -d -p 8080:8080 sa-webapp
```

By defaul this poins to the SA Python API running on the host on port 5000 by using the `host.docker.internal`
host which uses Docker networking to go from the container to the host.

### Verifying that it works

```shell script
curl http://localhost:8080/sentiment -H 'Content-Type: application/json' --data '{"sentence": "I hate you!"}'
```

## Pushing to Docker Hub

```shell script
docker tag sa-logic $DOCKER_USER_ID/k8s-training.sa-webapp
docker push $DOCKER_USER_ID/k8s-training.sa-webapp
```
