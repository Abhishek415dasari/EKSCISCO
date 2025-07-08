# Observability Stack for EKS

This directory contains manifests and Helm values for deploying the observability stack (Prometheus, Grafana, Loki, Jaeger) and Istio telemetry integration using Argo CD and GitOps.

## Layout

base/
  namespace.yaml           # Namespace for observability stack
  prometheus-values.yaml   # Prometheus Helm values
  grafana-values.yaml      # Grafana Helm values
  loki-values.yaml         # Loki Helm values
  jaeger-values.yaml       # Jaeger Helm values

telemetry/
  istio-telemetry.yaml     # Istio Telemetry custom resource for metrics and tracing
