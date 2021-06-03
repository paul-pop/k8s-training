## Building the Docker Container

```shell script
docker build -t sa-frontend .
```

## Running the Docker Container

```shell script
docker run -d -p 80:80 sa-frontend
```

### Verifying that it works

http://localhost:80

## Pushing to Docker Hub

```shell script
docker tag sa-logic $DOCKER_USER_ID/k8s-training.sa-frontend
docker push $DOCKER_USER_ID/k8s-training.sa-frontend
```
