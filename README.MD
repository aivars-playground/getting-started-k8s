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

ACCESSING POD
=============
*as a service, ip can change, usually do not connect directly
```shell
kubectl get pods -o wide
```

service has ip and DNS, access by DNS

Services: imperative approach, create service as a command
=============================
* programmatically expose  hello-pod (from pod.yml)
```shell
kubectl apply -f ./Pods/pod.yml
cd Services
kubectl expose pod hello-pod \
--name=hello-svc \
--target-port=8080 \
--type=NodePort
```
```shell
minikube ip
#192.168.49.2
kubectl get service
#hello-svc  8080:31515/TCP
curl http://127.0.0.1:31515
curl 192.168.49.2:31515
```

```shell
kubectl delete service --all
kubectl delete --all pods
```

