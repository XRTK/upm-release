# UPM Release (XRTK)

An atomic GitHub action to publish UPM (unity package manager) packages.

Part of the [Mixed Reality Toolkit (XRTK)](https://github.com/XRTK) open source project.

> This action does not have any dependency on the use of XRTK in your Unity project.

## How to use

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
          upm-auth-token: '${{ secrets.UPM_CREDENTIALS }}'
          github-token: '${{ secrets.GITHUB_TOKEN }}'
          github-pat: '${{ secrets.GITHUB_PAT }}'
          github-username: 'XRTK-Build-Bot'
          upm-server-address: 'http://upm.xrtk.io:4873'
```
