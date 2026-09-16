# Security Policy

## Scope

This repository is a public portfolio/demo project. Security improvements and responsible disclosure are welcome.

## Reporting a vulnerability

Please use a GitHub private security advisory when available rather than publishing exploit details in a public issue.

Include:

- affected component or file
- reproduction steps
- security impact
- suggested mitigation, if known

Never include passwords, API keys, tokens, private keys, or other secrets in a report.

## Security practices in this project

- Dependencies are pinned in `requirements.txt`.
- The Docker image runs as a non-root user.
- Compose enables a read-only filesystem, capability dropping, and `no-new-privileges`.
- Trivy can be used to scan the built image for vulnerabilities.
- No application credentials should be committed to the repository.
