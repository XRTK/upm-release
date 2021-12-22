# UPM Release (XRTK)

An atomic GitHub action to publish UPM (unity package manager) packages.

Part of the [Mixed Reality Toolkit (XRTK)](https://github.com/XRTK) open source project.

> This action does not have any dependency on the use of XRTK in your Unity project.

## How to use

```yaml
jobs:
  validate:
  strategy:
      matrix:
        runner: [ubuntu-latest, windows-latest, macos-latest]
    runs-on: ${{ matrix.runner }}

    outputs:
      editor-path: ${{ steps.unity-validate.outputs.editor-path }}
      project-path: ${{ steps.unity-validate.outputs.project-path }}
    steps:
      - uses: actions/checkout@v2

      - id: unity-validate
        uses: xrtk/unity-validate@main
          with:
            modules: 'android ios'

        run: echo ${{ steps.unity-validate.outputs.editor-path }}
        run: echo ${{ steps.unity-validate.outputs.project-path }}
```
