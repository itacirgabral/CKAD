> Crie um Secret `db-secret` com chave `PASSWORD=12345`
- k create secret generic db-secret --from-literal=PASSWORD=12345
- kubectl get secret db-secret -o jsonpath='{.data.password}' | base64 -d

> Crie um deployment que monta esse Secret como variável de ambiente.
- kubectl set env deployment/web-deploy --from=secret/db-secret

> Crie um Pod com `initContainer` que escreve em um `emptyDir` volume e um container principal que lê esse arquivo.
```yaml
apiVersion: v1
kind: Pod
metadata:
  name: web-pod
spec:
  containers:
  - name: nginx
    image: nginx:1.25
    envFrom:
    - secretRef:
        name: db-secret
    - secretRef:
        name: redis-secret
    - secretRef:
        name: sqlite-secret
    - secretRef:
        name: cassandra-secret
```
```yaml
apiVersion: v1
kind: Pod
metadata:
  name: web-pod
spec:
  containers:
  - name: nginx
    image: nginx:1.25
    env:
    - name: DB_PASS
      valueFrom:
        secretKeyRef:
          name: db-secret
          key: password
```

# apply
- kubectl apply --dry-run=client -f pod.yaml
- kubectl apply --dry-run=server -f pod.yaml
