# **Básico**

1. Crie um namespace chamado `ckad-ns`.
2. Inicie um Pod `nginx-pod` com a imagem `nginx:1.25` no namespace `ckad-ns`.
3. Exponha o pod como um `ClusterIP` service na porta 80.
4. Crie um ConfigMap `app-config` com a chave `LOG_LEVEL=debug` e monte no pod.
