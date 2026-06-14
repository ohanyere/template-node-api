# Deployment

CI is defined in `.github/workflows/ci.yaml` and calls platform standards from `ohanyere/platform-core`:

- `ohanyere/platform-core/.github/workflows/reusable-build-sign.yaml@main`
- `ohanyere/platform-core/.github/workflows/reusable-scan.yaml@main`
- `ohanyere/platform-core/.github/workflows/reusable-policy-check.yaml@main`

Images are published under the Docker Hub namespace `kuberpull`.

## Environments

- `dev`: fast promotion, lower resources
- `stage`: release candidate validation
- `prod`: guarded canary rollout

Render manifests locally:

```bash
make validate-k8s
```
