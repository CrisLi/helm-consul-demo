
```bash
helm repo add hashicorp https://helm.releases.hashicorp.com

kubectl apply -f namespace.yaml

helm install consul hashicorp/consul -f config.yaml -n infra

kubectl get secrets consul-consul-bootstrap-acl-token --template={{.data.token}} -n infra | base64 -D
```

```
# 404
consul kv get config/application/data

# 403
consul kv put config/application/data testing
```
