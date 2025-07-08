# Karpenter Autoscaler GitOps Manifests

This directory contains everything needed to install and configure Karpenter, the autoscaler for EKS, using GitOps (e.g., with Argo CD).

## Layout
base/
namespace.yaml # Namespace for Karpenter
karpenter-controller-sa.yaml # ServiceAccount & IAM annotation for Karpenter
karpenter-helm-values.yaml # Helm values for Karpenter controller deployment
karpenter-iam-role.yaml # IAM role/trust policy for node provisioning

provisioners/
default-provisioner.yaml # On-demand nodes, generic workloads
spot-provisioner.yaml # Spot instances, taints for batch workloads
zonal-provisioner.yaml # Zone-specific provisioning example


## Usage

1. **Install Karpenter Controller using Helm or Argo CD** (with these manifests).
2. **Apply Provisioner CRDs** in `provisioners/` to control node policies.
3. **Tune taints, labels, and requirements per workload/environment.

