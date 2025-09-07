https://kubernetes.io/docs/reference/kubectl/generated/kubectl_expose/
- kubectl expose pod nginx-pod -n ckad-ns --port=80
- kubectl expose pod nginx-pod -n ckad-ns --port=80 --dry-run=client -o yaml > se.yaml
- kubectl run curl --rm -it --image=curlimages/curl -n ckad-ns --restart=Never -- curl http://nginx-pod:80
