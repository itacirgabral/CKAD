Perfeito ✅ Aqui está a lista formatada como uma **tabela em Markdown**, separada por prioridade:

---

### 📌 Tópicos CKAD por prioridade

| Prioridade 🔥🟡🟢 | Recursos / Conceitos         | Observações                                |
| ----------------- | ---------------------------- | ------------------------------------------ |
| 🔥 Alta           | Pods                         | Criação, labels, annotations               |
| 🔥 Alta           | Deployments                  | Updates, rollbacks, estratégias            |
| 🔥 Alta           | ReplicaSets                  | Básico, ligado a Deployments               |
| 🔥 Alta           | Services                     | ClusterIP, NodePort, LoadBalancer          |
| 🔥 Alta           | ConfigMaps                   | Env vars e volumes                         |
| 🔥 Alta           | Secrets                      | Env vars e volumes                         |
| 🔥 Alta           | NetworkPolicies              | Ingress e egress simples                   |
| 🔥 Alta           | Probes                       | readiness, liveness, startup               |
| 🔥 Alta           | Namespaces                   | Organização, `kubectl -n`                  |
| 🟡 Média          | Jobs / CronJobs              | Execução única e agendada                  |
| 🟡 Média          | Volumes / PVCs               | Simples, sem StorageClasses avançadas      |
| 🟡 Média          | ServiceAccounts              | Uso básico em Pods                         |
| 🟡 Média          | Resource requests/limits     | CPU e memória                              |
| 🟡 Média          | Init containers              | Pré-processamento antes do main container  |
| 🟡 Média          | Sidecar containers           | Padrões sidecar simples                    |
| 🟡 Média          | Pod scheduling               | Taints/tolerations, nodeSelector, affinity |
| 🟢 Baixa          | Downward API                 | Infos do Pod em env vars/arquivos          |
| 🟢 Baixa          | Multi-container Pods         | Sidecar, adapter, ambassador               |
| 🟢 Baixa          | Ephemeral containers         | Debugging                                  |
| 🟢 Baixa          | Labels & selectors avançados | Seleções complexas                         |
| 🟢 Baixa          | SecurityContext              | Rodar como usuário não-root                |
| ❌ Fora           | Ingress                      | Não cai no CKAD                            |
| ❌ Fora           | RBAC avançado                | Apenas básico pode aparecer                |
| ❌ Fora           | Cluster administration       | CKA/CKS (etcd, upgrades, control plane)    |
| ❌ Fora           | CRDs                         | Fora do escopo                             |
| ❌ Fora           | Network plugins              | Não cobrado                                |
