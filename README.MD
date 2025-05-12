docker build - local
====================
```shell
docker build -t example.com/frontend:1.0 ./App/v1/
```
creates example.com/frontend:1.0

```shell
docker build -t example.com/frontend:2.0 ./App/v2/
```
creates example.com/frontend:2.0


PODS - simple
=============
```shell
kubectl apply -f ./Pods/pod.yml
```
```shell
kubectl get pods --watch
```

PODS - multi-cpntainer
=============
```shell
kubectl apply -f ./Pods/multi-pod.yml
```
main and helper can talk on a localhost
scraper exports nginx to prometheus logs...
```shell
kubectl get pods --watch
```

```shell
kubectl delete --all pods
```