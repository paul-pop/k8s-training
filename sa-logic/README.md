## Building the Docker Container

```shell script
docker build -t sa-logic .
```

## Running the Docker Container

```shell script
docker run -d -p 5000:5000 sa-logic
```

### Verifying that it works

Execute a POST on endpoint 

-> `localhost:5050/analyse/sentiment` or 

-> `<docker-machine ip>:5000/analyse/sentiment` Docker-machine ip has to be used if your OS doesn't provide native docker support. 

Request body:

```json
{
    "sentence": "I hate you!"
}
```

## Pushing to Docker Hub

```shell script
docker tag sa-logic $DOCKER_USER_ID/k8s-training.sa-logic
docker push $DOCKER_USER_ID/k8s-training.sa-logic
```
