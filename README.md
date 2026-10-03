# CuBlocky Marketplace

Community project marketplace for [CuBlocky](https://github.com/mouse114514/CuBlocky).

## Layout

    projects/
      manifest.json       catalog - one entry per approved project
      <slug>.cbp          project file
      <slug>.icon.png     marketplace thumbnail (not part of the project)
      <slug>/assets/      project image assets

## Consuming

`manifest.json` and every project file are served from `raw.githubusercontent.com`.
Browsing and downloading use zero GitHub API quota.

The CuBlocky in-app marketplace reads `projects/manifest.json` directly.

## Submitting

Open an issue with the `submission` label and attach:

- the `.cbp` file (split into `part001`, `part002`, ... when needed)
- the icon PNG
- each asset image

Then add a comment with the manifest:

    {
      "slug": "MyProject",
      "name": "My Project",
      "author": "your-login",
      "version": "1.0.0",
      "description": "what it does",
      "license": "MIT",
      "parts":  [{ "index": 0, "size": 1234, "sha256": "..." }],
      "assets": [{ "name": "sprite.png", "size": 4321, "sha256": "..." }]
    }

Submissions are reviewed manually. Approved projects are committed into
`projects/` and added to `projects/manifest.json`.
