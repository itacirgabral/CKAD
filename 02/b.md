
> execute um comando num pod
- kubectl run hello --image=busybox --restart=Never --dry-run=client -o yaml -- echo Hello World
mas fica faltando o command 
```yaml
apiVersion: v1
kind: Pod
metadata:
  name: hello-pod
spec:
  containers:
  - name: hello
    image: busybox
    command: ["/bin/sh","-c","echo Hello World"]
  restartPolicy: Never
```
- kubectl logs pods/hello

> Crie um Job que imprime Hello CKAD e finaliza.
- kubectl create job hello-ckad --image=busybox --dry-run=client -o yaml -- echo "Hello CKAD"
```yaml
apiVersion: batch/v1
kind: Job
metadata:
  name: hello-ckad
spec:
  template:
    spec:
      containers:
      - name: hello
        image: busybox
        command: ["echo", "Hello CKAD"]
      restartPolicy: Never
```

> Crie um CronJob que roda a cada minuto imprimindo tick
- kubectl create cronjob tick --image=busybox --schedule="* * * * *" -- echo tick
```yaml
apiVersion: batch/v1
kind: CronJob
metadata:
  name: tick
spec:
  schedule: "* * * * *"
  jobTemplate:
    spec:
      template:
        spec:
          containers:
          - name: tick
            image: busybox
            command: ["echo", "tick"]
          restartPolicy: Never
```
> crie um daemon
- kubectl create daemonset tick-daemon --image=busybox -- sh -c "while true; do echo tick; sleep 10; done"
```yaml
apiVersion: apps/v1
kind: DaemonSet
metadata:
  name: tick-daemon
spec:
  selector:
    matchLabels:
      app: tick-daemon
  template:
    metadata:
      labels:
        app: tick-daemon
    spec:
      containers:
      - name: tick
        image: busybox
        command: ["sh", "-c", "while true; do echo tick; sleep 10; done"]
```