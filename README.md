[![Release](https://github.com/JanCodeLab/workflows/actions/workflows/release.yml/badge.svg?event=workflow_dispatch)](https://github.com/JanCodeLab/workflows/actions/workflows/release.yml)
# Add tag workflow

This GitHub Action adds a tag to the current branch and pushes it to remote. It can also add or update the 'latest' tag.

## Usage

```yaml
add-tag:
    name: Release workflow
    uses: JanCodeLab/workflows/.github/workflows/add-tag.yml@latest
    with:
      tag: 'v1'
      is-latest: true
```

## Inputs

| Input | Description | Required | Default |
|-------|-------------|----------|---------|
| `tag` | Tag to add. | Yes | `''` |
| `is-latest` | Set current tag as latest | No | `true` |

# Add tag from package json workflow

This GitHub Action adds a tag to the current branch and pushes it to remote. It can also add or update the 'latest' tag.

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
| `version-file` | Tag to add. | Yes | `''` |
| `is-latest` | Set current tag as latest | No | `true` |

## Changelog
- v1 (latest)
  - Initial implementation of shared workflow functionalities