**Showcase for CISCO Sample Infrastructure**
# EKS GitOps Platform: Secure, Observable, Scalable Kubernetes on AWS

This repository demonstrates a production-ready, open-source reference platform for running microservices on AWS EKS (Elastic Kubernetes Service) using modern DevOps and Cloud Native best practices.

## **Platform Features**

- **Infrastructure as Code**: Automated AWS provisioning with Terraform (VPC, EKS, IAM, networking, more)
- **GitOps Workflow**: Declarative, auditable, and automated deployment using Argo CD
- **Service Mesh**: Istio for secure, observable, and flexible service-to-service traffic management (mTLS, routing, ingress, etc.)
- **Autoscaling**: Karpenter dynamically provisions EC2 nodes based on real workload needs (including spot, taints, zone-aware policies)
- **Observability**: Complete monitoring and tracing stack (Prometheus, Grafana, Loki, Jaeger), including Istio telemetry
- **Security and Policy Enforcement**: 
  - Kyverno admission policies (resource limits, privileged container blocking, label enforcement, no 'latest' tags, etc.)
  - Falco for runtime threat detection (unexpected shell access, suspicious file writes, etc.)
  - Trivy for container image scanning in CI and production
  - Gitleaks to prevent secrets from entering source control

---

## **Repository Structure**


1-terraform-infra/ # Terraform modules and IaC for AWS EKS, VPC, IAM, Karpenter, etc.
2-argocd-bootstrap/ # Argo CD installation and GitOps app-of-apps manifests
3-istio-service-mesh/ # Istio mesh, gateways, mTLS, advanced routing, and telemetry
4-karpenter/ # Karpenter autoscaler setup, IAM, and provisioner configs
5-observability-stack/ # Prometheus, Grafana, Loki, Jaeger (Helm/Kustomize), Istio telemetry
6-microservices/ # Example microservices (YAML/Helm), HPA, Istio routing
7-policy-enforcement/ # Kyverno admission control policies (security/governance)
8-runtime-threat-detection/ # Falco rules and deployment, alerting to Loki/Slack
9-image-scanning/ # Trivy image scanning (CI, CronJob, admission controller)
10-secret-detection/ # Gitleaks (pre-commit, GitHub Actions) for secret scanning

---

## **How do we make To Use**

1. **Provision Infrastructure**
   - Use `1-terraform-infra/` with Terraform to deploy foundational AWS resources and EKS cluster.

2. **Bootstrap GitOps**
   - Deploy Argo CD (`2-argocd-bootstrap/`) to manage all platform components declaratively from Git.

3. **Apply Service Mesh, Observability, Autoscaling, Security, and Microservices**
   - Argo CD will sync manifests from each component folder.
   - Extend/override with your own microservices or policies as needed.

4. **Automate Security & Compliance**
   - Kyverno, Falco, Trivy, and Gitleaks are integrated for full-stack, cloud-native security posture.

---

##  **Why This Platform?**

- **Secure by Default**: Zero trust, runtime detection, and strong policies
- **Scalable & Automated**: No manual EC2/node group management, auto-provisioning with Karpenter
- **Observable**: End-to-end tracing, monitoring, logging for platform and apps
- **Auditable & Repeatable**: All infra and ops as code, fully managed by GitOps

---

## **Sources and References**

- [AWS EKS Documentation](https://docs.aws.amazon.com/eks/latest/userguide/what-is-eks.html)
- [Terraform AWS Provider](https://registry.terraform.io/providers/hashicorp/aws/latest/docs)
- [Argo CD](https://argo-cd.readthedocs.io/)
- [Istio Service Mesh](https://istio.io/)
- [Karpenter Autoscaler](https://karpenter.sh/)
- [Prometheus](https://prometheus.io/), [Grafana](https://grafana.com/), [Loki](https://grafana.com/oss/loki/), [Jaeger](https://www.jaegertracing.io/)
- [Kyverno](https://kyverno.io/), [Falco](https://falco.org/), [Trivy](https://github.com/aquasecurity/trivy), [Gitleaks](https://github.com/gitleaks/gitleaks)

---

**Maintained by:** CISCO DevOps/Cloud Team  
*PRs and issues welcome!*
