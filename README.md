# Add tag action

This GitHub Action adds a tag to the current branch and pushes it to remote. It can also add or update the 'latest' tag.

## Usage

```yaml
- name: Add tag
  uses: duchacekjan/action-add-tag@v1
  with:
    tag: 'v1.0.0'  # Tag to add
    package-json-file: 'path/to/package.json'  # Path to package.json file
    is-latest: true  # Set current tag as latest
    is-test: false # Test mode. Does not pushes to remote
```

## Inputs

| Input | Description | Required | Default |
|-------|-------------|----------|---------|
| `tag` | Tag to add. If defined, other tag options are ignored| No | `''` |
| `package-json-file` | Retrieves tag as version from package.json file | No | `''` |
| `is-latest` | Set current tag as latest | No | `true` |

## Outputs

| Output | Description |
|--------|-------------|
| `tag` | Tag added |

## Example: Adding a tag from package.json

```yaml
jobs:
  add-tag:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      
      - name: Add tag
        uses: duchacekjan/action-add-tag@v1
        with:
          package-json-file: 'path/to/package.json'
```

## Changelog
- v1 (latest)
  - Initial implementation of action functionality