# Rain Effect Add-on

A transparent, customizable rain effect for
[MyWallpaper](https://github.com/MyWallpapers/MyWallpaper), implemented
against the canonical Canvas add-on runtime.

## Features

- **Realistic rain simulation** with smooth Canvas 2D rendering
- **Glow effects** with adjustable intensity
- **Wind control** with adjustable angle and variation
- **Transparent rendering** that overlays any wallpaper
- **Layer-scoped settings** acknowledged by the host runtime

## Installation and development

The repository is published through the canonical MyWallpaper add-on
admission workflow. For local testing:

```bash
pnpm install
pnpm dev
```

For a distributable build:

```bash
pnpm build
pnpm test
```

Use MyWallpaper's developer tools to load the local Vite origin. The release
bundle is `dist/index.html` plus `dist/assets/addon.js`.

## Settings

| Setting | Description | Default |
|---------|-------------|---------|
| Rain color | Color of the raindrops | `#a8c8e8` |
| Rain intensity | Number of raindrops (100–50000) | 200 |
| Fall speed | How fast the rain falls (0.5–3x) | 1.7 |
| Drop length | Length of rain streaks (5–50px) | 42 |
| Drop width | Thickness of raindrops (0.5–4px) | 0.8 |
| Wind angle | Angle of rain (-45–45 degrees) | -5 |
| Wind variation | Random variation in wind direction | 0 |
| Opacity | Transparency of raindrops (0.1–1) | 0.6 |
| Enable glow | Add a soft glow effect | On |
| Glow intensity | Brightness of the glow (0.1–1) | 0.3 |

Lower **Rain intensity** or disable **Enable glow** if the layer needs less
CPU usage.

## License

MIT License

## Publishing

Merge the source and matching manifest/package version into the reviewed default
branch, wait for quality checks, then push a new immutable `v<version>` tag.
Open this add-on's management page in MyWallpaper and select that tag to request
publication with an active lifetime entitlement.

MyWallpaper resolves the exact public repository and commit, dispatches its
pinned central workflow, rebuilds and verifies the artifacts, and publishes the
immutable transport from the platform repository. The add-on repository needs
no publication workflow or MyWallpaper credential. Do not pre-create a GitHub
release: a source tag alone does not publish the add-on to the catalogue.

Each accepted newer release is available for new installations. Existing
wallpapers remain pinned to their exact release until explicitly changed.
