# ArgoCD App Configuration

```bash
kubectl apply -f .\nginx-app.yaml
kubectl apply -f nginx-rollout.yaml

kubectl port-forward -n argocd svc/argocd-server 8080:443

kubectl argo rollouts get rollout nginx-rollout -n argocd --watch
kubectl argo rollouts promote nginx-rollout -n argocd
