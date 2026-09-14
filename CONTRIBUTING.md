# Contributing

Thanks for contributing to **DevOps Health API**.

## Development flow

1. Create a feature branch from `main`.
2. Make a focused change.
3. Run the test suite locally:

```bash
pytest -q
```

4. Build and run the container:

```bash
docker compose up --build
```

5. Open a pull request with a clear summary and testing notes.

## Pull requests

Keep changes small and production-minded. Avoid committing secrets, local environment files, generated artifacts, or credentials.

CI automatically validates tests, builds the Docker image and runs a Trivy HIGH/CRITICAL vulnerability scan.
