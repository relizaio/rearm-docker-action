# `rearm-docker-action`

## About

GitHub Action to build a Docker image, push it to the registry, and submit the release metadata to [ReARM](https://github.com/relizaio/rearm).

## Usage

```yaml
steps:
- uses: relizaio/rearm-docker-action@1.6.0
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
The action supports the following inputs:

- `rearm_api_id`: The component API ID obtained from Rearm.
- `rearm_api_key`: The component API Key obtained from Rearm.
- `registry_username`: Username for the image registry.
- `registry_password`: Password for the image registry.
- `registry_host`: Image registry host.
- `image_namespace`: Namespace of the image on registry.
- `image_name`: Name of the image.
- `path`: Path relative to the root of the repo (default is '.').
- `dockerfile_name`: Name of the dockerfile (default is 'Dockerfile').
- `rearm_component_id`: component UUID if an org-wide key is used.
- `push_latest_tag`: Whether to push image with 'latest' tag also, optional, default: `true`
- `platform_architectures`: A comma-separated list of platform architectures, optional, default: `'linux/amd64'`; supported platforms: `'linux/amd64 linux/arm64 linux/s390x linux/arm/v7 linux/arm/v6'`
- `rearm_api_url`: ReARM API URL, optional, default: `https://demo.rearmhq.com`.
- `ci_metadata`: Metadata for CI run, (Optional - default is GitHub).
- `enable_sbom`: Generates SBOM and stores it along with the artifact, optional, default: `false`.
- `source_code_sbom_type`: Generates SBOM based on source code analysis, possible values: `npm`, `other`, `none`, optional, default: `none`.
- `enable_public_cosign_sigstore`: Sign deliverables and SBOMs using public sigstore via cosign, optional, default: `false`.
- `enable_codeql`: Enable CodeQL analysis, optional, default: `false`.
- `codeql_language`: Language to analyze with CodeQL, optional, default: `none`.
- `successful_build_lifecycle`: Status on build success to be set on ReARM (DRAFT or ASSEMBLED), optional, default: `ASSEMBLED`.
- `enable_securesbom`: Enable SecureSBOM by ShiftLeftCyber signing of SBOMs, optional, default: `false`.
- `securesbom_pub_key_id`: Public key ID to sign with SecureSBOM by ShiftLeftCyber, optional, default: empty.
- `securesbom_host`: SecureSBOM (by ShiftLeftCyber) host, optional, default: empty.
- `securesbom_api_key`: SecureSBOM (by ShiftLeftCyber) API key, optional, default: empty.
