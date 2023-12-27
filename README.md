# Godot CI/CD

Workflows for exporting and pushing Godot Engine projects to itch.io.

## Usage

**Example `.github/workflows/export-and-push.yml`**
```yaml
name: Export and push

on: push

jobs:

  export-and-push-windows:
    name: Windows
    uses: LF/godot-ci/.github/workflows/export-and-push-windows.yml@v1
    secrets: inherit
    with:
      name: my-project
      target: user/my-project:windows
      version: "3.5.3"

  export-and-push-macos:
    name: macOS
    uses: LF/godot-ci/.github/workflows/export-and-push-macos.yml@v1
    secrets: inherit
    with:
      name: My Project
      target: user/my-project:macos
      version: "3.5.3"

  export-and-push-linux:
    name: Linux
    uses: LF/godot-ci/.github/workflows/export-and-push-linux.yml@v1
    secrets: inherit
    with:
      name: my-project
      target: user/my-project:linux
      version: "3.5.3"

  export-and-push-web:
    name: Web
    uses: LF/godot-ci/.github/workflows/export-and-push-web.yml@v1
    secrets: inherit
    with:
      name: my-project
      target: user/my-project:web
      version: "3.5.3"
```

These workflows use the following actions:

- [LF/butler-login-action](https://github.com/LF/butler-login-action)
- [LF/butler-push-action](https://github.com/LF/butler-push-action)
- [LF/godot-export-action](https://github.com/LF/godot-export-action)
- [LF/godot-setup-action](https://github.com/LF/godot-setup-action)

and use these images from Docker Hub:

- [lfdev/godot-headless](https://hub.docker.com/r/lfdev/godot-headless) ([repo](https://github.com/LF/docker-godot-headless))
- [lfdev/butler](https://hub.docker.com/r/lfdev/butler) ([repo](https://github.com/LF/docker-butler))
