## Building and deploying the sample
```
# Build the container on your local machine
docker build -t {username}/helloworld-nodejs .

# Push the container to docker registry
docker push {username}/helloworld-nodejs
```

```
kubectl apply --filename k8s/service.yaml
```

```
kubectl get ksvc helloworld-nodejs  --output=custom-columns=NAME:.metadata.name,URL:.status.url
NAME                URL
helloworld-nodejs   http://helloworld-nodejs.default.1.2.3.4.xip.io
```