# Policy Enforcement (Kyverno)

This directory contains Kyverno admission control policies for Kubernetes.
The following security and governance controls are included:

- No privileged containers allowed
- Mandatory resource requests and limits
- No 'latest' tag allowed in container images
- Required labels on all pods

## Usage

1. Install [Kyverno](https://kyverno.io/docs/installation/) in your cluster (can be managed with Argo CD or Helm).
2. Apply or sync the policies in the `policies/` folder to your cluster.
3. These policies will enforce best practices and help secure your workloads.

Each policy is ready for use with GitOps tools like Argo CD.
