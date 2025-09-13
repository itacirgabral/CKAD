```yaml
apiVersion: v1
kind: Pod
metadata:
  name: pod-init-example
spec:
  volumes:
    - name: shared-data
      emptyDir: {}
  initContainers:
    - name: init-write
      image: busybox
      command: ['sh', '-c', 'echo "Hello from initContainer" > /data/message.txt']
      volumeMounts:
        - name: shared-data
          mountPath: /data
  containers:
    - name: main-read
      image: busybox
      command: ['sh', '-c', 'cat /data/message.txt && sleep 3600']
      volumeMounts:
        - name: shared-data
          mountPath: /data
```
- https://kubernetes.io/docs/concepts/workloads/pods/init-containers/
- https://kubernetes.io/docs/concepts/storage/volumes/#emptydir