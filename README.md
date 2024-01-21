# apache-superset
# Installation
## 0. Add helm repo
```shell
helm repo add superset https://apache.github.io/superset
helm search repo superset
```
## 1. Genarate secret and add secret to my-values.yaml
```shell
openssl rand -base64 42
```
Result : 
```shell
sdH5DCISevZwqmHquB/Mp+8r5v7b8SBxSvZYAXiTJIQce4vRPHxaEbU4
```
## 2. Install and Run
```shell
helm upgrade --install --values my-values.yaml superset superset/superset
```
Result : 
```shell
kubectl get pods
NAME                                    READY   STATUS      RESTARTS   AGE
superset-celerybeat-7cdcc9575f-k6xmc    1/1     Running     0          119s
superset-f5c9c667-dw9lp                 1/1     Running     0          4m7s
superset-f5c9c667-fk8bk                 1/1     Running     0          4m11s
superset-init-db-zlm9z                  0/1     Completed   0          111s
superset-postgresql-0                   1/1     Running     0          6d20h
superset-redis-master-0                 1/1     Running     0          6d20h
superset-worker-75b48bbcc-jmmjr         1/1     Running     0          4m8s
superset-worker-75b48bbcc-qrq49         1/1     Running     0          4m12s
```

Ref: 
- Running Apache Superset on Kubernetes: https://superset.apache.org/docs/installation/running-on-kubernetes/   
- Security recommendation: https://superset.apache.org/docs/installation/running-on-kubernetes/#important-settings

