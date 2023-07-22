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
helm upgrade -i istio-istiod istio/istiod \
  --namespace istio-system
```

Install Istio Gateway (Ingress controller):
```bash
helm upgrade -i istio-gateway istio/gateway \
  --namespace istio-ingress \
  --create-namespace
```

### kiali

Add kiali repo:
```bash
helm repo add kiali https://kiali.org/helm-charts
helm repo update
```

Install kiali:
```bash
helm upgrade -i kiali-server kiali/kiali-server \
  --namespace istio-system \
  --set auth.strategy="anonymous"
```


Create Namespace:
```bash
kubectl create ns testing
kubectl label ns testing istio-injection=enabled
```

Create nginx deployment:
```bash
kubectl -n testing create deployment nginx --image=nginx:alpine
```


