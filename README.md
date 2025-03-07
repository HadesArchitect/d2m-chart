# Helm Chart for Doom in Kubernetes (kubedoom)

## Prerequisites

K8s cluster with a public IP on a worker node

## Installation

### Deploy the chart
```
helm repo add d2m https://hadesarchitect.github.io/d2m-chart/
helm install d2m d2m/d2m
```

### Connect and go!
- Get the pod's node: `kubectl describe pod d2m-kubedoom`
- Get the public IP: `kubectl get node NODE -o jsonpath="{.status.addresses[?(@.type=='ExternalIP')].address}"`

**Open that IP in a browser using port `6080`. Have fun!**

## Todo
Nice-to-have ideas that weren't implemented because of time restrictions
- Terraform k8s cluster deployment
- Ansible chart deployment
- Proper ingress instead of NodeIP
- svc instead of in-pod communication