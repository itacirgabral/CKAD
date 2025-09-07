# CKAD
A prova permite abrir apenas:

* [https://kubernetes.io/docs/](https://kubernetes.io/docs/)
* [https://kubernetes.io/blog/](https://kubernetes.io/blog/)
* [https://github.com/kubernetes/](https://github.com/kubernetes/)

Sugestão de treino:

* Sempre que começar um exercício → **não use o que lembra de cabeça**, abra a doc e tente achar o exemplo.
* Treine buscar:

# **Básico**

1. Crie um namespace chamado `ckad-ns`.
2. Inicie um Pod `nginx-pod` com a imagem `nginx:1.25` no namespace `ckad-ns`.
3. Exponha o pod como um `ClusterIP` service na porta 80.
4. Crie um ConfigMap `app-config` com a chave `LOG_LEVEL=debug` e monte no pod.

# **Workloads**

5. Crie um Deployment `web-deploy` com 3 réplicas de `nginx:1.25`, exposto como NodePort.
6. Atualize o deployment para a imagem `nginx:1.26`.
7. Crie um Job que imprime `Hello CKAD` e finaliza.
8. Crie um CronJob que roda a cada minuto imprimindo `tick`.

# **Configuração e Storage**

9. Crie um Secret `db-secret` com chave `PASSWORD=12345`.
10. Crie um Pod que monta esse Secret como variável de ambiente.
11. Crie um Pod com `initContainer` que escreve em um `emptyDir` volume e um container principal que lê esse arquivo.

# **Networking**

12. Crie uma NetworkPolicy que só permite o Pod `frontend` falar com o Pod `backend` na porta 80.
13. Crie um Ingress que roteia `/` para o serviço `web-deploy`.

# **Observabilidade**

14. Corrija um Pod que tenta rodar a imagem inexistente `nginx:abc`.
15. Crie um Pod com `livenessProbe` em `/healthz` porta 8080.
16. Limite um Pod a `cpu: 200m` e `memory: 128Mi`.
