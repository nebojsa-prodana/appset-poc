# appset-poc

Testing ArgoCD ApplicationSet in different scenarios.

Requires:

- two kind clusters, one as a control plane and one as a remote target

```console
kind create cluster --name eu-west-1a-1
kind create cluster
```

- [applicationset](https://github.com/argoproj-labs/applicationset) controller installed

## appset-helm-dep

This ApplicationSet install an helm chart that has a dependency on another helm chart. This is useful to pull in third-party chart or if you have a different ops team maintining the helm charts.

### Pros

- Easy to manage. Bumping a dependency is just updating a value in the `Chart.yaml`.
- Small footprint, needs only a directory with at least a `Chart.yaml`.
- Can use `valueFiles` to have an additional value file per cluster.

### Cons

- No dependencies health checks. For example, passing a non-existing version of `go-infrabin` doesn't cause any issue with the application, that looks like healthy and synced.
- If you have a lot of clusters with the same overrides, can add a lot of repetition.

## appset-helm

TODO
