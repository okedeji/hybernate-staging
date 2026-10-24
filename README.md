# hybernate-staging

The staging environment for [Napwake](https://github.com/napwake/napwake)'s pre-launch test: a small GKE cluster, `napwake` in the `napwake-test` project, that runs like a team's non-production estate, so Napwake can be used as a beta user would use it before launch. It ran Hybernate, Napwake's old name, on the `prelaunch` cluster until 2026-10-24.

Argo CD applies everything here from Git:

- `bootstrap/`: the Argo CD application that applies the rest
- `argocd-apps/`: an Argo CD application for each part. The platform around the apps (ingress-nginx, Prometheus, KEDA), and each staging app.
- `apps/`: the staging apps Napwake manages, on the `workloads` node pool, and the load generator that keeps them busy during working hours

Napwake itself is installed from its docs at docs.napwake.dev, so the test also tests the docs.
