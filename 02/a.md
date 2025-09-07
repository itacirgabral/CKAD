> Crie um Deployment `web-deploy` com 3 réplicas de `nginx:1.25`, exposto como NodePort.
- k create deployment web-deploy --image=nginx:1.25 --replicas=3  --dry-run=client -o yaml
- k expose deployment web-deploy --type=NodePort  --port=80
- k get service
- k get nodes -o wide