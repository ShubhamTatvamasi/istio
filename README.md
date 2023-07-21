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

Install Istio CRD:
```bash
helm upgrade -i istio-base istio/base \
  --namespace istio-system \
  --create-namespace
```

Install IstioD:
```bash
helm upgrade -i istiod istio/istiod \
  --namespace istio-system
```

Create Namespace:
```bash
kubectl create ns testing
kubectl label ns testing istio-injection=enabled
```
