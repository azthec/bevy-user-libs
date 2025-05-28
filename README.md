# bevy-user-libs

Third-party Bevy libraries managed as git submodules for controlled dependency management.

## Overview

This repository contains third-party Bevy plugins and libraries as git submodules, allowing for:
- Explicit version control of dependencies
- Code review of library updates before integration
- Reproducible builds with pinned versions
- Easy access to latest upstream code when desired

## Usage

### Setup
```bash
git clone --recursive https://github.com/your-username/bevy-user-libs.git
```

### Adding
```bash
git submodule add https://github.com/author/bevy-plugin.git path/to/bevy-plugin
git commit -m "Add bevy-plugin submodule"
```

### Updating
```bash
# all submodules
git submodule update --remote

# specific submodule
cd path/to/bevy-plugin
git pull origin main
cd ../..
git add path/to/bevy-plugin
git commit -m "Update bevy-plugin to latest"
```

### Integration

In your `Cargo.toml`:
```toml
[dependencies]
bevy_plugin_name = { path = "../bevy-user-libs/path/to/bevy-plugin" }
```

## Compatibility

| bevy | lib                    |
|------|------------------------|
| 0.16 | bevy_hanabi            |
| 0.16 | bevy_lit               |
| 0.16 | bevy_mod_outline       |
| 0.16 | bevy_spatial           |
| 0.16 | bevy_voronoi           |
| 0.16 | bevy_wind_waker_shader |

