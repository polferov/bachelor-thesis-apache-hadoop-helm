# Customized Hadoop Base Image

This image is modified from [comcast/kube-yarn](https://github.com/Comcast/kube-yarn/tree/add-hadoop-image-versions) and [mgit-at/helm-hadoop-3](https://github.com/mgit-at/helm-hadoop-3). Currently, native libraries are not been included.

## Build and Push the Image

```bash
# Set version
HADOOP_VERSION=3.3.2

# Build
docker buildx build --push --platform "linux/arm64,linux/amd64" -t farberg/apache-hadoop:latest -t farberg/apache-hadoop:$KNOXHADOOP_VERSION_VERSION .
```

## Testing with minikube

If you are running locally with minikube and want to try your images without pushing them to a registry, build the images on the minikube VM first:

```bash
eval $(minikube docker-env)
# use the build command from above
```
