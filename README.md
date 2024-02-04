# Setup Crane

Installs [`crane`](https://github.com/google/go-containerregistry/tree/main/cmd/crane) for use in [Buildkite]() builds.

## Example

```yaml
steps:
- name: Copy docker image
  plugins:
  - sj26/setup-crane
  command: crane copy "$SOURCE" "$TARGET"
```

Works well in combination with other plugins like [docker compose](https://github.com/buildkite-plugins/docker-compose-buildkite-plugin) which can build and push images and [ecr](https://github.com/buildkite-plugins/ecr-buildkite-plugin) which logs in to registries.

## Select crane version to install

By default, the latest released version of crane will be installed.

You can select a version with the version parameter:

```yaml
steps:
- plugins:
  - sj26/setup-crane:
      version: v0.5.1
  command: crane version
```

## Thanks

Inspired by the  [setup-crane](https://github.com/imjasonh/setup-crane) GitHub Action.
