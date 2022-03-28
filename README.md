# UPM Release (XRTK)

An atomic GitHub action to publish UPM (unity package manager) packages.

Part of the [Mixed Reality Toolkit (XRTK)](https://github.com/XRTK) open source project.

> This action does not have any dependency on the use of XRTK in your Unity project.

## How to use

1. Setup GitHub repository or organization secrets:
  - UPM_TOKEN - npm token used to sign into the server or service.
  - GITHUB_PAT - A Personal Access Token for GitHub to make commits and publish the release.

```yaml
jobs:
  publish:
    runs-on:  ubuntu-latest

    steps:
      - uses: xrtk/upm-release@main
        name: publish upm package
        with:
          upm-username: 'xrtk-build-bot'
          upm-email: 'xrtk-build-bot@xrtk.io'
          upm-server-address: 'http://upm.xrtk.io:4873'
          upm-auth-token: '${{ secrets.UPM_TOKEN }}'
          github-username: 'XRTK-Build-Bot'
          github-pat: '${{ secrets.GITHUB_PAT }}'
          github-token: '${{ secrets.GITHUB_TOKEN }}'
```
