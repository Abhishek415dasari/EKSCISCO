# Runtime Threat Detection (Falco)

This directory contains all manifests for deploying Falco, custom runtime rules, and alerting configuration for Kubernetes clusters.

Includes:
- Falco deployment via Helm (GitOps-ready)
- Custom rules (shell in container, file changes)
- Alert forwarding to Loki and Slack (or other alert systems)

## Usage

1. Install Falco in your cluster via Argo CD or Helm, using the files in `base/`.
2. Sync custom rules from `rules/` for advanced detection.
3. Apply alert configurations in `alerts/` to forward Falco events to Loki and/or external alerting systems.
