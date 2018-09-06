# Setup Gitea on Kubernetes Cluster

## Cloned from

1. helm

Mostly cloned from [[WIP] Adds Gitea to the incubator #3408](https://github.com/helm/charts/pull/3408), and [cdrage's original source](https://github.com/cdrage/charts/tree/add-gitea/incubator/gitea), and upgrade Gitea version to 1.5, modified PVC using nfs-client, using `initContainers` to initial rights settings.

2. manifest

Cloned from [jmferrer/gitea-kubernetes](https://github.com/jmferrer/gitea-kubernetes) and [norbertvannobelen/gitea-kubernetes](https://github.com/norbertvannobelen/gitea-kubernetes), and upgrade Gitea version to 1.5 and modified PVC using nfs-client.

## Two ways to setup Gitea on Kubernetes cluster

0. Pre

Prepare Kubernetes cluster ready before install Gitea;
Prepare ingress, namespace, secret etc.

1. Helm

Clone this repo first:

```
git clone https://github.com/isaron/gitea-kubernetes.git && cd gitea-kubernetes/helm
```

Check `values.yaml` if you want modify yours config, and save as `myvalue.yaml`, then install using Helm:
```
helm install --name gitea --namespace env .
```

2. Manifest

Clone this repo first:
```
git clone https://github.com/isaron/gitea-kubernetes.git && cd gitea-kubernetes/manifest
```

Check all files and save them, then install:
```
chmod +x createConfigMap.sh && ./createConfigMap.sh
kubectl apply -f .
```
