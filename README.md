# istio

Add Istio Repo:
```bash
helm repo add istio https://istio-release.storage.googleapis.com/charts
helm repo update
```

Search Istio repos:
```bash
helm search repo istio/
```

Install Istio base:
```bash
helm upgrade -i istio-base istio/base \
  --namespace istio-system \
  --create-namespace \
  --set defaultRevision=default
```

Install IstioD:
```bash
helm upgrade -i istiod istio/istiod \
  --namespace istio-system
```

