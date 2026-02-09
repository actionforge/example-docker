# example-docker

[![view-action-graph](https://img.shields.io/github/actions/workflow/status/actionforge/example-docker/workflow.yml?label=View%20Action%20Graph)](https://app.actionforge.dev/github/actionforge/example-docker/main/.github/workflows/graphs/build.act)

A simple Hello World Docker image, built and pushed to ghcr.io using an [Actionforge](https://actionforge.dev) graph as the CI/CD pipeline.

## Run

```bash
docker build -t hello-world .
docker run hello-world
```

## Graph

The build pipeline is defined as an Actionforge graph in [`.github/workflows/graphs/build.act`](.github/workflows/graphs/build.act):

```
checkout -> docker/login-action (ghcr.io) -> docker/build-push-action
```

It runs on every push to `main`, on pull requests, and on manual dispatch.
