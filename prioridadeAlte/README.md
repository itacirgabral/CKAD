Perfeito 🚀 — você está montando um plano de treino bem direcionado para o CKAD.
Vou te propor **20 exercícios apenas de prioridade 🔥 alta**, todos práticos, que você deve ser capaz de fazer **muito rápido** (copiar da documentação oficial ou gerar via `kubectl`).

Eles estão divididos por tema, e sempre com instrução **curta e objetiva** para simular o enunciado do exame.
⚠️ **Sem respostas aqui** — só os enunciados, como você pediu.

---

# 📝 Exercícios CKAD – Prioridade 🔥 Alta

## 1. Pods

1. Crie um Pod chamado `nginx-pod` com a imagem `nginx:1.25`.
2. Crie um Pod chamado `busybox-pod` com a imagem `busybox` que execute `sleep 3600`.
3. Crie um Pod `annotated-pod` com label `tier=frontend` e annotation `owner=teamA`.

---

## 2. Deployments & ReplicaSets

4. Crie um Deployment chamado `web-deploy` com 3 réplicas da imagem `nginx`.
5. Aplique um update para trocar a imagem de `nginx:1.25` para `nginx:1.26`.
6. Faça rollback para a versão anterior do Deployment `web-deploy`.
7. Escale o Deployment `web-deploy` para 5 réplicas.
8. Liste e identifique o ReplicaSet associado ao `web-deploy`.

---

## 3. Services

9. Exponha o Deployment `web-deploy` como Service `ClusterIP` na porta 80.
10. Crie um Service `NodePort` chamado `node-svc` para o Deployment `web-deploy`, expondo a porta 80.
11. Crie um Service `LoadBalancer` chamado `lb-svc` para o Deployment `web-deploy`.

---

## 4. ConfigMaps

12. Crie um ConfigMap chamado `app-config` com chave `APP_MODE=production`.
13. Crie um Pod `cm-pod` que injete `APP_MODE` como variável de ambiente a partir do ConfigMap.
14. Monte o mesmo ConfigMap como volume no caminho `/etc/config`.

---

## 5. Secrets

15. Crie um Secret chamado `db-secret` com `username=admin` e `password=1234`.
16. Crie um Pod `secret-pod` que use esse Secret como variáveis de ambiente.
17. Monte o Secret `db-secret` como volume em `/etc/secret`.

---

## 6. NetworkPolicies

18. Crie uma NetworkPolicy chamada `deny-all` que bloqueie todo o tráfego de entrada para Pods no namespace `default`.
19. Crie uma NetworkPolicy chamada `allow-nginx` que permita tráfego **somente de Pods com label `app=frontend`** para os Pods com label `app=nginx`.

---

## 7. Probes

20. Crie um Pod `probe-pod` com a imagem `nginx` que tenha:

* readinessProbe em `GET /` porta 80 (delay 5s, período 10s)
* livenessProbe em `GET /` porta 80 (delay 10s, período 15s)

---

📌 **Dicas de treino**:

* Sempre comece tentando gerar via `kubectl create ... --dry-run=client -o yaml`.
* Saiba achar na documentação oficial: [kubernetes.io/docs](https://kubernetes.io/docs/home/).
* Treine **apagar e recriar rápido** (`kubectl delete pod/deploy/cm/...`).
* Use namespaces (`-n`) em alguns exercícios para se acostumar.

---

Quer que eu monte também um **setup mínimo para os exercícios de NetworkPolicies** (com Pods de teste `nginx` e `busybox`), para você já poder validar bloqueios e liberações?
