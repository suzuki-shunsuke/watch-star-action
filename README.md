# watch-star-action

Notify your repository's stars to GitHub Issues

![image](https://github.com/suzuki-shunsuke/test-github-action/assets/13323303/451757c6-0b25-4b6b-88ba-4ec7dc0a7bbf)

## Motivation

By subscribing the issue, you can receive the notification immediately when the repository gets a star.
GitHub Stars will motivate you.

## How to use

1. Create a GitHub Issue to send comments
1. Add a GitHub Actions Workflow

```yaml
---
name: watch
on:
  watch:
    types:
      - started
jobs:
  test:
    runs-on: ubuntu-latest
    permissions:
      issues: write
    steps:
      - uses: suzuki-shunsuke/watch-star-action@main
        with:
          number: 167 # Change the issue number
```

## Note

This action requires GitHub CLI (gh).
This action assumes that the workflow run is triggered by a watch:started event.

## Inputs

### Required

- `number` (integer): The GitHub Issue number

### Optional

- `body` (string): The comment body
- `github_token` (string): GitHub Access Token to post comments. The permission `issues: write` is necessary
- `repo` (string): GitHub Repository to post comments. The default is `$GITHUB_REPOSITORY`

## Outputs

Nothing.

## LICENSE

[MIT](LICENSE)
