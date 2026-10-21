# hybernate-staging

The staging environment for [Hybernate](https://github.com/okedeji/hybernate)'s pre-launch test: a small GKE cluster that runs like a team's non-production estate, so Hybernate can be used as a beta user would use it, for a few weeks, before launch.

Argo CD applies everything here from Git:

- `bootstrap/`: the Argo CD application that applies the rest
- `platform/`: what the cluster needs around the apps (ingress, Prometheus, KEDA)
- `apps/`: the staging apps Hybernate manages, on the `workloads` node pool, and the load generator that keeps them busy during working hours

Hybernate itself is installed by hand from its docs, so the test also tests the docs.
