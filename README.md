# "tbzeefinal" - Ansible Execution Environment

"this is a text execution environment"

## 📁 Files

| File | Purpose |
|------|---------|
| `execution-environment.yml` | Main ansible-builder configuration (UBI9 Python 3.12) |
| `requirements.txt` | Python dependencies (pip packages) |
| `requirements.yml` | Ansible Galaxy collections |
| `bindep.txt` | System packages (RPM/DEB) |

## 🚀 Quick Start

```bash
# Install tools
pip install ansible-builder ansible-navigator

# Build the execution environment
ansible-builder build -t "tbzeefinal":latest .

# Test it works
ansible-navigator exec --execution-environment-image "tbzeefinal":latest -- ansible --version
```

## 🧪 Testing

```bash
# Basic test - check collections
ansible-navigator exec --execution-environment-image "tbzeefinal":latest -- ansible-galaxy collection list

# Run a test playbook
ansible-navigator run test-playbook.yml --execution-environment-image "tbzeefinal":latest
```

## 🔄 CI/CD


This repository is configured with automated CI/CD workflows that will:

1. Build the execution environment image
2. Run tests to validate the image
3. Publish the image to "ghcr.io"
4. Create a release with proper version tagging

The image will be available at: `"ghcr.io"/"tbzeefinal":latest`

