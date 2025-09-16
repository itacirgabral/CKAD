```yaml
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: web-deploy-ingress
  namespace: default
  annotations:
    nginx.ingress.kubernetes.io/rewrite-target: /
spec:
  rules:
  - http:
      paths:
      - path: /
        pathType: Prefix
        backend:
          service:
            name: web-deploy
            port:
              number: 80
```