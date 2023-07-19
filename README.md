## Semver Action

This GitHub Action extracts the version from `github.ref` and outputs it in various formats.

### Outputs
- `version`: The pushed version, for example "v1.2.7".
- `version-without-v`: The pushed version, without the `v` prefix, for example "1.2.7".
- `major`: The semver major version, for example "1" in the case of "v1.2.3-ALPHA.0+BUILD.1".
- `minor`: The semver minor version, for example "2" in the case of "v1.2.3-ALPHA.0+BUILD.1".
- `patch`: The semver patch version, for example "3" in the case of "v1.2.3-ALPHA.0+BUILD.1".
- `prerelease`: The semver prerelease version, for example "ALPHA.0" in the case of "v1.2.3-ALPHA.0+BUILD.1".
- `build`: The semver build version, for example "BUILD.1" in the case of "v1.2.3-ALPHA.0+BUILD.1".

### Usage

```yaml
steps:
  - name: Get Version
    uses: maltoze/get-version-action@v1
    id: get_version
  - name: Build and Deploy
    with:
      version: ${{ steps.get_version.outputs.version }}
```

### Credits
[battila7/get-version-action](https://github.com/battila7/get-version-action)