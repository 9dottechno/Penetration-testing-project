# CI/CD Integration Documentation for AI-Powered Pentest Framework

## GitHub Actions
- Workflow file: `.github/workflows/pentest.yml`
- Runs on push to `main` or manually.
- Installs dependencies, runs `pentest_framework.py`, uploads all reports as artifacts.

## GitLab CI/CD
- Pipeline file: `.gitlab-ci.yml`
- Stage: `pentest`
- Uses Python 3.10 image, installs dependencies, runs `pentest_framework.py`, saves all reports as artifacts.

## Jenkins
- Pipeline file: `Jenkinsfile`
- Stages: Install dependencies, run pentest, archive reports.

## Requirements
- Python 3.10+
- All dependencies in `requirements.txt` plus:
  - selenium
  - python-docx
  - reportlab
  - hvac
  - boto3
  - azure-identity
  - azure-keyvault-secrets

## Secrets Management
- Use environment variables or vault integrations for sensitive keys.
- Supported: HashiCorp Vault, AWS Secrets Manager, Azure Key Vault.

## Output
- Reports: `pentest_report.json`, `pentest_report.pdf`, `pentest_report.docx`, `dashboard_data.json`, `attestation_certificate.json`

## Example Usage
- Add your secrets to CI/CD environment variables or vaults.
- Push code to trigger pipeline.
- Download reports from pipeline artifacts.
