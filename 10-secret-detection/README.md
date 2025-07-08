# Secret Detection with Gitleaks

This directory provides tools to prevent secrets from being committed to your repository.

**Features:**
- **Pre-commit hook** with Gitleaks for local scanning before commits
- **GitHub Actions workflow** to scan all code on every push and pull request

## Usage

### 1. Pre-commit Hook

- Make sure [pre-commit](https://pre-commit.com/) is installed locally:
pip install pre-commit

- Install the hook in your repo:
pre-commit install

- Now every commit is scanned for secrets before it’s added!

### 2. GitHub Actions

- The provided workflow (`ci/gitleaks.yml`) runs on every push/PR to prevent secrets from being pushed.

## References

- [Gitleaks Documentation](https://github.com/gitleaks/gitleaks)
- [Pre-commit Documentation](https://pre-commit.com/)
