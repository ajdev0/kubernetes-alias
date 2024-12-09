# General Kubernetes aliases
```
alias k="kubectl"
alias kg="kubectl get"
alias kd="kubectl describe"
alias ka="kubectl apply -f"
alias kdel="kubectl delete"
alias kex="kubectl exec -it"
alias kl="kubectl logs"
alias kcon="kubectl config"
alias kctx="kubectl config use-context"
alias kns="kubectl config set-context --current --namespace"
```
# Namespace shortcuts
```
alias kgns="kubectl get namespaces"
alias kcdns="kubectl config set-context --current --namespace"
```
# Deployment shortcuts
```
alias kgd="kubectl get deployments"
alias kdd="kubectl describe deployment"
alias ksd="kubectl scale deployment"
alias kerd="kubectl edit deployment"
alias krrd="kubectl rollout restart deployment"
alias krld="kubectl rollout status deployment"
```
# Pod shortcuts
```
alias kgp="kubectl get pods"
alias kdp="kubectl describe pod"
alias klp="kubectl logs pod"
alias kep="kubectl exec -it pod"
```
# Service shortcuts
```
alias kgs="kubectl get services"
alias kds="kubectl describe service"
```

# ConfigMap & Secret shortcuts
```
alias kgcm="kubectl get configmaps"
alias kdcm="kubectl describe configmap"
alias kgsec="kubectl get secrets"
alias kdsec="kubectl describe secret"
alias kcm="kubectl create configmap"
alias ksec="kubectl create secret"
```
# Persistent Volume and Persistent Volume Claim
```
alias kgpv="kubectl get pv"
alias kdpv="kubectl describe pv"
alias kgpvc="kubectl get pvc"
alias kdpvc="kubectl describe pvc"
```
# Ingress shortcuts
```
alias kging="kubectl get ingress"
alias kding="kubectl describe ingress"
```
# Nodes shortcuts
```
alias kgn="kubectl get nodes"
alias kdn="kubectl describe node"
```
# Advanced Kubernetes Aliases
# Apply multiple YAML files in a directory
```
alias kaf="kubectl apply -f"
```
# Delete all pods in the current namespace
```
alias kdelpods="kubectl delete pods --all"
```
# Port-forward a pod
```
alias kpf="kubectl port-forward"
```
# Get events in the current namespace
```
alias kge="kubectl get events --sort-by='.metadata.creationTimestamp'"
```
# Debugging shortcuts
```
alias ktop="kubectl top nodes"
alias ktopn="kubectl top pods --namespace"
```
# List all resources in a namespace
```
alias kga="kubectl get all"
```
# View cluster info
```
alias kci="kubectl cluster-info"
```
# Dry-run for debugging
```
alias kdapply="kubectl apply -f --dry-run=client"
```
# Access Kubernetes Dashboard (if installed)
```
alias kdash="kubectl proxy"
```
# Switch between clusters and contexts
```
alias klsctx="kubectl config get-contexts"
alias kswitch="kubectl config use-context"
```
