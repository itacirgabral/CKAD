> Crie um Pod com `livenessProbe` em `/healthz` porta 8080.
```yaml
apiVersion: v1
kind: Pod
metadata:
  name: liveness-http
spec:
  containers:
  - name: liveness
    image: registry.k8s.io/e2e-test-images/agnhost:2.40
    args:
    - liveness
    livenessProbe:
      httpGet:
        path: /healthz
        port: 8080
      initialDelaySeconds: 3 # default 0
      periodSeconds: 3 # default 10
      # timeoutSeconds: 1
      # successThreshold: 1
      # failureThreshold: 3
```
