# appset-poc

Test ApplicationSet in a kind cluster.

Requires:

- [Kind](https://kind.sigs.k8s.io/docs/user/quick-start/#installation)
- [argocd](https://argoproj.github.io/argo-cd/getting_started/#1-install-argo-cd)
- [applicationset](https://github.com/argoproj-labs/applicationset) controller installed

## Usage

To install an AppSet that generates one Application targeting the local kind cluster

```console
kubectl apply -f appset-goinfra.yaml
```
