# kubernetes-alias

Short, memorable `kubectl` aliases for everyday Kubernetes work: pods, deployments, services, config, storage, contexts, namespaces, and debugging. Works in **bash** and **zsh**.

```bash
kgp                 # kubectl get pods
kl my-pod -f        # kubectl logs my-pod -f
kns staging         # switch the current namespace to "staging"
krrd api            # kubectl rollout restart deployment api
```

## Install

Clone the repo and source the aliases file from your shell config:

```bash
git clone https://github.com/ajdev0/kubernetes-alias.git ~/.kubernetes-alias
echo 'source ~/.kubernetes-alias/kubernetes-aliases.sh' >> ~/.zshrc   # or ~/.bashrc
source ~/.zshrc
```

Requires `kubectl` on your `PATH`. `ktop` / `ktopn` also need [metrics-server](https://github.com/kubernetes-sigs/metrics-server) in the cluster.

## Aliases

### General Kubernetes aliases

| Alias | Runs |
|---|---|
| `k` | `kubectl` |
| `kg` | `kubectl get` |
| `kd` | `kubectl describe` |
| `ka` | `kubectl apply -f` |
| `kdel` | `kubectl delete` |
| `kex` | `kubectl exec -it` |
| `kl` | `kubectl logs` |
| `kcon` | `kubectl config` |
| `kctx` | `kubectl config use-context` |
| `kns` | `kubectl config set-context --current --namespace` |

### Namespace shortcuts

| Alias | Runs |
|---|---|
| `kgns` | `kubectl get namespaces` |
| `kcdns` | `kubectl config set-context --current --namespace` |

### Deployment shortcuts

| Alias | Runs |
|---|---|
| `kgd` | `kubectl get deployments` |
| `kdd` | `kubectl describe deployment` |
| `ksd` | `kubectl scale deployment` |
| `kerd` | `kubectl edit deployment` |
| `krrd` | `kubectl rollout restart deployment` |
| `krld` | `kubectl rollout status deployment` |

### Pod shortcuts

| Alias | Runs |
|---|---|
| `kgp` | `kubectl get pods` |
| `kdp` | `kubectl describe pod` |
| `klp` | `kubectl logs` |
| `kep` | `kubectl exec -it` |

### Service shortcuts

| Alias | Runs |
|---|---|
| `kgs` | `kubectl get services` |
| `kds` | `kubectl describe service` |

### ConfigMap & Secret shortcuts

| Alias | Runs |
|---|---|
| `kgcm` | `kubectl get configmaps` |
| `kdcm` | `kubectl describe configmap` |
| `kgsec` | `kubectl get secrets` |
| `kdsec` | `kubectl describe secret` |
| `kcm` | `kubectl create configmap` |
| `ksec` | `kubectl create secret` |

### Persistent Volume and Persistent Volume Claim

| Alias | Runs |
|---|---|
| `kgpv` | `kubectl get pv` |
| `kdpv` | `kubectl describe pv` |
| `kgpvc` | `kubectl get pvc` |
| `kdpvc` | `kubectl describe pvc` |

### Ingress shortcuts

| Alias | Runs |
|---|---|
| `kging` | `kubectl get ingress` |
| `kding` | `kubectl describe ingress` |

### Nodes shortcuts

| Alias | Runs |
|---|---|
| `kgn` | `kubectl get nodes` |
| `kdn` | `kubectl describe node` |

### Apply multiple YAML files in a directory

| Alias | Runs |
|---|---|
| `kaf` | `kubectl apply -f` |

### Delete all pods in the current namespace (destructive: use with care)

| Alias | Runs |
|---|---|
| `kdelpods` | `kubectl delete pods --all` |

### Port-forward a pod

| Alias | Runs |
|---|---|
| `kpf` | `kubectl port-forward` |

### Get events in the current namespace

| Alias | Runs |
|---|---|
| `kge` | `kubectl get events --sort-by='.metadata.creationTimestamp` |

### Debugging shortcuts

| Alias | Runs |
|---|---|
| `ktop` | `kubectl top nodes` |
| `ktopn` | `kubectl top pods --namespace` |

### List all resources in a namespace

| Alias | Runs |
|---|---|
| `kga` | `kubectl get all` |

### View cluster info

| Alias | Runs |
|---|---|
| `kci` | `kubectl cluster-info` |

### Dry-run for debugging

| Alias | Runs |
|---|---|
| `kdapply` | `kubectl apply --dry-run=client -f` |

### Access Kubernetes Dashboard (if installed)

| Alias | Runs |
|---|---|
| `kdash` | `kubectl proxy` |

### Switch between clusters and contexts

| Alias | Runs |
|---|---|
| `klsctx` | `kubectl config get-contexts` |
| `kswitch` | `kubectl config use-context` |

## Notes

- Aliases only expand the start of a command, so add arguments as usual: `kdp my-pod`, `kex my-pod -- sh`, `kpf svc/api 8080:80`.
- `kdelpods` deletes **every pod in the current namespace**. Check your context (`kcon current-context`) and namespace before using it.
- Some aliases are intentional synonyms for muscle memory (`ka`/`kaf`, `kns`/`kcdns`, `kctx`/`kswitch`).
