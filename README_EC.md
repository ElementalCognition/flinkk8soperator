# Instructions for building and deploying a new image


In all the following replace `<HASH>` with latest commit hash.


## Build and push new image

```
docker build -t us-east4-docker.pkg.dev/elementalcognition-app-source/docker-all/lyft/flinkk8soperator:<HASH> --progress=plain .
```

```
docker push us-east4-docker.pkg.dev/elementalcognition-app-source/docker-all/lyft/flinkk8soperator:<HASH>
```

## Edit the deployment directly, for testing
```
kubectl edit deploy lyft-flink-flink-operator -n lyft-flink-operator
```

And change the previous hash to the new one (I changed two locations - one in the image name and one elsewhere).

## Update the infrastructure repo

Once changes are tested, to make them permanent, merge a PR in the infrastrucutre repo, for example:
https://github.com/ElementalCognition/infrastructure/commit/875ed9c6f657300d2ca221ff11c610d63368e918
 

