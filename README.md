[docs](https://knative.dev/docs/serving/samples/hello-world/helloworld-nodejs/)

## Building and deploying the sample
```
# Build the container on your local machine
docker build -t {username}/knative-nodejs .

docker build -t straucorp/knative-nodejs .

# Push the container to docker registry
docker push {username}/knative-nodejs

docker push straucorp/knative-nodejs
```

```
kubectl apply --filename k8s/service.yaml
```

```
kubectl get ksvc helloworld-nodejs  --output=custom-columns=NAME:.metadata.name,URL:.status.url
NAME                URL
helloworld-nodejs   http://helloworld-nodejs.default.1.2.3.4.xip.io
```