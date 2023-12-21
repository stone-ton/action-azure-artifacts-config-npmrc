# Github Action: Azure Artifacts .npmrc configuration

Github Action that configures the .npmrc for accessing private packages published on Azure Artifacts.

This action should automate the steps described on this doc: https://docs.microsoft.com/en-us/azure/devops/artifacts/get-started-npm?view=azure-devops&tabs=windows#set-up-your-npmrc-files

## Inputs

### `organization`

**Required** The organization name.  Example: `vizir`.

### `project`

**Required** The project name. This action only works for Feeds created inside a Project.  Example: `vizir`.

### `feeds`

**Required** Comma separated list of feeds to authenticate.  Example: `feed1,feed2`.

### `username`

**Required** The user name that will be set on `~/.npmrc`. Example: `vizir`.

### `token`

**Required** The Personal Access Token (PAT). Example: `abcdef1234567890`.

## Example usage

```
uses: Vizir/action-azure-artifacts-config-npmrc@1.0
with:
  organization: vizir
  project: vizir
  feeds: feed1,feed2
  username: vizir
  token: ${{ secrets.AZURE_PAT }}
```
