# create-pr-action

This action automates the process of creating a new Pull Request on a GitHub repository. It uses the GitHub GraphQL API to create a Pull Request with the specified base branch, head branch, and title. Optionally, it can also enable auto-merge for the created Pull Request.

## Inputs:
 - personal-access-token (required): A personal access token with the necessary permissions to create a Pull Request on the target repository.
 - base-branch (required): The name of the branch that the Pull Request should be based on.
 - head-branch (required): The name of the branch that the changes should be pulled from.
 - pr-title (required): The title of the Pull Request.
 - pr-body (optional): The body of the Pull Request (as Markdown).
 - enable-auto-merge (optional): A boolean flag to indicate whether auto-merge should be enabled for the created Pull Request. Default is true.
 - merge-method (optional): The merge method when auto-merge is enabled: MERGE / REBASE / SQUASH (default: SQUASH).


## Usage
```yaml
---
- name: Create Pull Request
  uses: ChainReaction-LTD/create-pr-action@v1
  with:
    personal-access-token: ${{ secrets.GITHUB_TOKEN }}
    base-branch: main
    head-branch: feature-branch
    pr-title: Add new feature
    pr-body: New feature details
    enable-auto-merge: true
    merge-method: SQUASH
```