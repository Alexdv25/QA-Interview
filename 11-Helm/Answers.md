# Helm Interview Answers

1. **What is Helm and what problem does it solve in Kubernetes?**
   Helm is a package manager for Kubernetes. It bundles a set of manifests (Deployments, Services, ConfigMaps, etc.) into a single versioned "chart" with configurable values, so you can install, upgrade, and roll back a whole application as one unit instead of applying raw YAML files by hand.

2. **What is a Helm chart and what is its directory structure?**
   A chart is a directory with a defined layout:
   - `Chart.yaml` — chart metadata (name, version, appVersion)
   - `values.yaml` — default configuration values
   - `templates/` — Kubernetes manifest templates using Go templating
   - `charts/` — bundled subchart dependencies
   - `templates/NOTES.txt` — post-install usage notes shown to the user

3. **What is the difference between `helm install` and `helm upgrade`?**
   `helm install` creates a brand new release from a chart. `helm upgrade` updates an existing release with a new chart version or new values, applying only the diff to already-running resources. `helm upgrade --install` does either depending on whether the release already exists.

4. **What are Helm values files and how do overrides work?**
   `values.yaml` in the chart provides defaults. You override them at install/upgrade time with `-f custom-values.yaml` or `--set key=value`. Precedence (highest to lowest): `--set` flags, then `-f` files in the order given, then the chart's own `values.yaml`.

5. **What is a Helm release and how is it tracked?**
   A release is a named, versioned instance of a chart installed into a cluster. Helm stores release state (the rendered manifests and metadata) as Secrets (or ConfigMaps) in the target namespace, which is how `helm history` and `helm rollback` know what was deployed and when.

6. **How do you roll back a failed Helm release?**
   `helm rollback <release> <revision>` reverts to a previous stored revision. `helm history <release>` lists revisions to pick from. Helm also has `--atomic` on install/upgrade, which automatically rolls back if the operation fails.

7. **What are Helm hooks and when would you use them?**
   Hooks are annotated manifests (e.g. `helm.sh/hook: pre-install`, `post-upgrade`) that run at specific points in a release lifecycle — commonly used for DB migrations before a new version rolls out, or cleanup jobs after an upgrade/uninstall.

8. **What is the difference between a Helm chart dependency and a subchart?**
   A subchart is a chart nested inside `charts/` of a parent chart. A dependency is declared in `Chart.yaml` (or `Chart.lock`) pointing to a chart repo/version; `helm dependency update` downloads it into `charts/`. In practice a dependency becomes a subchart once fetched — the terms describe the same relationship from declaration vs. filesystem perspective.

9. **How does Helm templating work, and what happens if a template renders invalid YAML?**
   Templates use Go's `text/template` syntax plus Sprig functions, combined with values at render time via `helm template` or during install/upgrade. If the rendered output is invalid YAML or fails Kubernetes API validation, the install/upgrade fails before anything is applied — `helm template` or `helm install --dry-run` is the way to catch this ahead of time.

10. **How do you test a chart before installing it in production?**
    - `helm lint` — checks chart structure and common mistakes
    - `helm template` — renders manifests locally without touching the cluster, useful for diffing or piping into a validator like `kubeconform`
    - `helm install --dry-run --debug` — simulates the install against the live cluster's API for validation without persisting anything
    - `helm test` — runs test hooks (`helm.sh/hook: test`) against an already-installed release
