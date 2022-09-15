# Hasura

## How to set PostgreSQL URL

change `value: postgres://<username>:<password>@hostname:<port>/<dbname>` in `deployment.yaml`

## How to create the Kubernetes deplyment and service

```sh
$ kubectl create -f deployment.yaml
$ kubectl create -f svc.yaml
```

## How to open Hasura console

First of All,  check the kubernetes

```sh
$ kubectl get svc
NAME         TYPE           CLUSTER-IP      EXTERNAL-IP   PORT(S)        AGE
hasura       LoadBalancer   10.96.214.240   localhost     80:30303/TCP   4m
kubernetes   ClusterIP      10.96.0.1       <none>        443/TCP        8m
```

Secondly, open `http://localhost/ in web browser

# References

- <https://hasura.io/docs/latest/deployment/deployment-guides/kubernetes/>
