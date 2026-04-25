# Secure DevSecOps App

This repository demonstrates a production-grade DevSecOps CI pipeline fully implemented in GitHub Actions.

## Features

- Secure Python Flask app
- Multi-stage DevSecOps pipeline
- SAST (Semgrep)
- Dependency scanning (pip-audit)
- Secret scanning (Gitleaks)
- Container scanning (Trivy)
- SBOM generation (Syft - CycloneDX)
- Artifact storage and traceability

## Pipeline Flow

1. **Scan Job**
   - Static code analysis
   - Dependency vulnerability scan
   - Secret detection
   - Uploads reports

2. **Build Job**
   - Runs only if scans pass
   - Builds Docker image tagged with commit SHA
   - Runs container vulnerability scan
   - Generates SBOM
   - Marks build as trusted
   - Uploads artifacts

## Artifacts Produced

- `semgrep-report.json`
- `dependency-report.json`
- `gitleaks-report.json`
- `trivy-report.json`
- `sbom.json`
- `image-id.txt`
- `trusted-build.txt`

## Security Practices

- No secrets in code
- Least privilege container
- Reproducible builds
- Full audit trail via artifacts
