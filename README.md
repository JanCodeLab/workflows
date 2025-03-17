[![Release](https://github.com/JanCodeLab/workflows/actions/workflows/release.yml/badge.svg?event=workflow_dispatch)](https://github.com/JanCodeLab/workflows/actions/workflows/release.yml)
# Add tag workflow

This GitHub workflow adds a tag to the current branch and pushes it to remote. It can also add or update the 'latest' tag.

## Usage

```yaml
add-tag:
    name: Release workflow
    uses: JanCodeLab/workflows/.github/workflows/add-tag.yml@latest
    with:
      tag: 'v1.0-test'
      is-latest: true
```

## Inputs

| Input | Description | Required | Default |
|-------|-------------|----------|---------|
| `tag` | Tag to add. | Yes | `''` |
| `remote-name` | Remote name of target repository | No | `origin` |
| `is-latest` | Set current tag as latest | No | `true` |

## Outputs

| Output | Description | Required | Default |
|-------|-------------|----------|---------|
| `tag-exists` | Tag exists on the remote already | Yes | `''` |

# Add tag from package json workflow

This GitHub workflow adds a tag to the current branch and pushes it to remote. It can also add or update the 'latest' tag.

## Usage

```yaml
add-tag:
    name: Release workflow
    uses: JanCodeLab/workflows/.github/workflows/add-tag-from-package.yml@latest
    with:
      version-file: './package.json'
      is-latest: true
```

## Inputs

| Input | Description | Required | Default |
|-------|-------------|----------|---------|
| `version-file` | Path to package.json file containing version. | Yes | `''` |
| `remote-name` | Remote name of target repository | No | `origin` |
| `is-latest` | Set current tag as latest | No | `true` |

## Outputs

| Output | Description | Required | Default |
|-------|-------------|----------|---------|
| `tag-exists` | Tag exists on the remote already | Yes | `''` |

# Check if tag exists on remote

This GitHub workflow checks if tag exitst on given remote.

## Usage

```yaml
check-tag:
    name: Release workflow
    uses: JanCodeLab/workflows/.github/workflows/check-tag-exists.yml@latest
    with:
      tag: '1.0-test'
```

## Inputs

| Input | Description | Required | Default |
|-------|-------------|----------|---------|
| `tag` | Tag to add. | Yes | `''` |
| `remote-name` | Remote name of target repository | No | `origin` |

## Outputs

| Output | Description | Type |
|-------|-------------|---------|
| `exists` | Tag exists on the remote already | `boolean` |
| `tag` | Checked tag | `string` |

# Create and push tags

This GitHub workflow checks if tag exitst on given remote.

## Usage

```yaml
create-and-push:
    name: Release workflow
    uses: JanCodeLab/workflows/.github/workflows/create-push-tags@latest
    with:
      tag: 'v1'
      is-latest: true
```

## Inputs

| Input | Description | Required | Default |
|-------|-------------|----------|---------|
| `tag` | Tag to add. | Yes | `''` |
| `remote-name` | Remote name of target repository | No | `origin` |
| `is-latest` | Set current tag as latest | No | `true` |

## Changelog
- v1.3 (latest)
  - Documented all reusable workflows
  - Fixed missing documentation
  - Unified naming of output parameters
- v1.2
  - Added permissions to workflows
- v1.1
  - Added tag existence check
- v1
  - Initial implementation of shared workflow functionalities