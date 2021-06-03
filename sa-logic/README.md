## Building the Docker Container

```shell script
docker build -t sa-logic .
```

## Running the Docker Container

```shell script
docker run -d -p 5000:5000 sa-logic
```

### Verifying that it works

```shell script
curl http://localhost:5000/analyse/sentiment -H 'Content-Type: application/json' --data '{"sentence": "I hate you!"}'
```

## Pushing to Docker Hub

```shell script
docker tag sa-logic $DOCKER_USER_ID/k8s-training.sa-logic
docker push $DOCKER_USER_ID/k8s-training.sa-logic
```
