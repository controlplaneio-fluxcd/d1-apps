# d1-apps

This repository is managed by the dev teams who are responsible for
the delivery of applications to the Kubernetes cluster fleet.

## Scope and Access Control

This repository is used to define the application components such as:

- Flux HelmRepositories (pointing to the application Helm charts in container registries)
- Flux HelmReleases for the applications with custom configuration per environment

This repository is reconciled on the cluster fleet by Flux as the **namespace admin**
and can't contain Kubernetes cluster-wide definitions such as CRDs, Cluster Roles, Namespaces, etc.

The platform team that manages the `d1-fleet` repository is responsible for assigning the
namespaces to the dev teams and configuring Flux with the necessary RBAC to reconcile
the `d1-apps` repository.

Access to this repository is restricted to the dev teams and the
[Flux bot account](https://github.com/controlplaneio-fluxcd/d1-fleet?tab=readme-ov-file#create-a-github-account-for-flux).
