# Helm Chart for Doom in Kubernetes (kubedoom)

## Prerequisites

K8s cluster with a public IP on a worker node

## Installation

### Deploy the chart
```
helm repo add d2m https://hadesarchitect.github.io/d2m-chart/
helm install d2m d2m/d2m
```

### Get the node public IP
```
kubectl describe pod d2m-kubedoom 
kubectl get node YOURNODENAME -o jsonpath="{.status.addresses[2].address}"
```

### Install VNC Client
We recommend installing [TigerVNC](https://tigervnc.org/), but any modern VNC client should work.

### Connect and go!
Open VNC connection using the node public IP and port `5900`. Provide password `idbehold` and have fun!


## Todo
Nice-to-have ideas that weren't implemented because of time restrictions
- Terraform k8s cluster deployment
- Ansible chart deployment
- Proper ingress instead of NodeIP
- VNC client in a browser to avoid installation of a VNC client on a client side