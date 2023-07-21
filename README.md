# istio

Add Istio Repo:
```bash
helm repo add istio https://istio-release.storage.googleapis.com/charts
helm repo update
```

Install Istio base:
```bash
helm upgrade -i istio-base istio/base \
  --namespace istio-system \
  --create-namespace \
  --set defaultRevision=default
```
