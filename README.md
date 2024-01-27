# UPM Release (XRTK)

An atomic GitHub action to publish UPM (unity package manager) packages.

Part of the [Mixed Reality Toolkit (XRTK)](https://github.com/XRTK) open source project.

> This action does not have any dependency on the use of XRTK in your Unity project.

## How to use

Requirements:

- Setup GitHub repository or organization secrets:
  - UPM_TOKEN - npm token used to sign into the server or service.
- Workflow or Job permissions set to `write`

```yaml
jobs:
  publish:
    permissions:
      contents: write
    runs-on:  ubuntu-latest

    steps:
      - uses: xrtk/upm-release@v5
        name: publish upm package
        with:
          upm-username: 'xrtk-build-bot'
          upm-email: 'xrtk-build-bot@xrtk.io'
          upm-server-address: 'http://upm.xrtk.io:4873'
          upm-auth-token: '${{ secrets.UPM_TOKEN }}'
          github-username: 'XRTK-Build-Bot'
          github-token: '${{ secrets.GITHUB_TOKEN }}'
```
