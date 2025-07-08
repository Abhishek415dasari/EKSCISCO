# Container Image Scanning with Trivy

This directory contains examples for integrating Trivy vulnerability scanning:
- In CI (GitHub Actions)
- As a Kubernetes CronJob for regular scanning
- As an Admission Controller (webhook) to block risky images (optional/advanced)

## Usage

- **ci/trivy-scan.yml**: GitHub Actions workflow for scanning on push/PR
- **k8s/trivy-cronjob.yaml**: Kubernetes CronJob to scan images on a schedule
- **admission/trivy-operator-install.yaml**: Trivy Operator to block critical CVEs at deploy time
