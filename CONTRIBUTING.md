# Contributing

Thanks for contributing to **DevOps Health API**.

## Development workflow

1. Create a feature branch from `main`.
2. Keep changes focused and documented.
3. Create and activate a virtual environment.
4. Install dependencies:

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
```

5. Run tests:

```bash
python -m pytest -q
```

6. Build and run locally:

```bash
docker compose up --build
```

7. Open a pull request with a concise summary, validation steps, and any security considerations.

## Repository standards

- Do not commit credentials, API keys, certificates, `.env` files, virtual environments, or generated artifacts.
- Prefer small, reviewable changes.
- Keep dependency versions explicit and review upgrades before merging.
- Preserve the non-root and hardened container runtime unless there is a documented reason to change it.

## Continuous integration

The repository keeps CI configuration available for **manual execution only**. Automatic push and pull-request runs are intentionally disabled for this portfolio repository.
