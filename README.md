# kubernetes-setup-series

## Install MicroK8s

### Install MicroK8s on Linux

```sh
sudo snap install microk8s --classic
```
Don’t have the `snap` command? Get set up for snaps

### Check the status while Kubernetes starts

```sh
microk8s status --wait-ready
```

### Turn on the services you want

```sh
microk8s enable dashboard dns registry istio
```

Try `microk8s enable --help` for a list of available services and optional features.
`microk8s disable <name>` turns off a service.

### Start using Kubernetes

```sh
microk8s kubectl get all --all-namespaces
```

If you mainly use MicroK8s you can make our kubectl the default one on your command-line with `alias mkctl="microk8s kubectl"`.
Since it is a standard upstream kubectl,
you can also drive other Kubernetes clusters with it by pointing to the respective kubeconfig file via the `--kubeconfig` argument.

### Access the Kubernetes dashboard

```sh
microk8s dashboard-proxy
```

### Start and stop Kubernetes to save battery

Kubernetes is a collection of system services that talk to each other all the time.
If you don’t need them running in the background then you will save battery by stopping them.
`microk8s start` and `microk8s stop` will do the work for you.


## References

- <https://microk8s.io/#install-microk8s>
