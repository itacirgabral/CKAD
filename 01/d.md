- https://kubernetes.io/docs/tasks/configure-pod-container/configure-pod-configmap/
- kubectl create configmap app-config --from-literal=LOG_LEVEL=debug
- (não funciona em Pod direto) kubectl set env --from=configmap/app-config deployment/myapp
- kubectl get pod nginx-pod -n ckad-ns -o yaml --export
```yaml
apiVersion: v1
kind: Pod
metadata:
  name: nginx-pod
  namespace: ckad-ns
spec:
  containers:
  - name: nginx
    image: nginx
    envFrom:
    - configMapRef:
        name: app-config
```
```yaml
apiVersion: v1
kind: Pod
metadata:
  name: nginx-pod
  namespace: ckad-ns
spec:
  containers:
  - name: nginx
    image: nginx
    env:
    - name: LOG_LEVEL
      valueFrom:
        configMapKeyRef:
          name: app-config
          key: LOG_LEVEL
```