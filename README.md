# helm-wordpress :circus_tent:

Repository mit Helm Chart für Wordpress mit MySQL :smirk:

# Prerequists

Folgende CustomResourceDefinitions sind zwingend notwendig und müssen vorab manuell installiert werden:

- templates/customResourceDefinitions.yaml

```sh
$ kubectl apply -f ./templates/customResourceDefinitions.yaml
```

- namespace muss aktuell noch manuell angelegt werden bis diese Issue gelöst ist: https://github.com/helm/helm/issues/6794

# Lokale Bash-History für Stable Wordpress Helm Chart als Vorlage

```sh
$ helm repo add stable https://kubernetes-charts.storage.googleapis.com/
$ helm search repo wordpress
$ helm repo update
$ helm help
$ mkdir stable
$ cd stable
$ helm pull stable/wordpress
$ helm install -h
$ helm create test
$ helm install . --dry-run --debug --generate-name --skip-crds
$ helm install wordpress-merlin . --skip-crds --namespace merlin
$ helm upgrade --install wordpress-merlin . --namespace merlin
$ helm ls -n merlin
$ helm delete wordpress-merlin -n merlin
```
