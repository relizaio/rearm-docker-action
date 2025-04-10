# `rearm-docker-action`

## About

GitHub Action to Build a Docker image, push it to the registry and submit the release metadata to [ReARM](https://github.com/relizaio/rearm).

## Usage

```yaml
steps:
- uses: relizaio/rearm-docker-action@1.0.0
  with:
    rearm_api_id: <api-id-obtained-from-rearmhub>
    rearm_api_key: <api-key-obtained-from-rearmhub>
    registry_username: <image-registry-username>
    registry_password: <image-registry-password>
    registry_host: <image-registry-host>
    image_namespace: <registry-namespace>
    image_name: <image-name>
```

## Inputs
The actions supports the following inputs:

- `rearm_api_id`: The component API ID obtained from Rearm.
- `rearm_api_key`: The component API Key obtained from Rearm.
- `registry_username`: Username for the image registry.
- `registry_password`: Password for the image registry.
- `registry_host`: Image registry host.
- `image_namespace`: Namespace of the image on registry.
- `image_name`: Name of the image.
- `path`: Path to the relative to root of the repo (default is '.').
- `dockerfile_name`: Name of the dockerfile (default is 'Dockerfile').
- `rearm_component_id`: component UUID if an org-wide key is used.
- `push_latest_tag`: Whether to push image with 'latest' tag also, optional, default: `true`
- `platform_architectures`: A comma separated list of platform architectures, optional, default: `'linux/amd64'`; supported platforms: `'linux/amd64 linux/arm64 linux/s390x linux/arm/v7 linux/arm/v6'`

