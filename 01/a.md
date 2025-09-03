- https://kubernetes.io/docs/tasks/administer-cluster/namespaces/#creating-a-new-namespace

```yaml
apiVersion: v1
kind: Namespace
metadata:
  name: ckad-ns
```
- kubectl create namespace ckad-ns
- kubectl create namespace ckad-ns --dry-run=client -o yaml