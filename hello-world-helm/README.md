# Hello World (Helm)

```sh
# Create namespace
kubectl apply -f namespace.yaml

# Install Helm chart and get manifest
helm install hello-world . -n hello-world-helm
helm install hello-world . -n hello-world-helm --set favorite.drink=slurm
helm get manifest hello-world -n hello-world-helm

# Uninstall Helm chart
helm uninstall hello-world -n hello-world-helm

# Render template without installing it
helm install hello-world . --debug --dry-run
helm install hello-world . --debug --dry-run --set favorite.drink=slurm
```
