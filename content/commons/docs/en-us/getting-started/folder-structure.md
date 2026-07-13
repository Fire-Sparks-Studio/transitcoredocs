---
title: Folder Structure
description: Learn how TransitCore organizes addon files and how each directory is used.
---

# Folder Structure

Every TransitCore addon follows a standardized directory structure.

Using the recommended layout keeps projects organized, improves maintainability and allows TransitCore to automatically discover resources without requiring additional configuration.

<Alert severity="info">

TransitCore automatically scans known directories inside an addon. Following the recommended structure ensures that resources are discovered consistently across every project.

</Alert>

## Standard structure

A typical addon is organized as follows.

```text title="Addon structure"
MyAddon/
├── addon.yaml
├── scripts/
├── models/
├── textures/
├── animations/
├── sounds/
├── lang/
├── ui/
└── README.md
```

Each directory has a dedicated purpose.

## Root directory

The root directory contains the addon manifest and every resource required by the addon.

```text title="Root directory"
MyAddon/
├── addon.yaml
├── scripts/
├── models/
└── ...
```

TransitCore identifies an addon by locating the `addon.yaml` manifest.

Without this file, the directory is ignored.

## scripts/

The `scripts` directory contains every LuaTC script executed by the addon.

```text title="Scripts directory"
scripts/
├── main.luatc
├── vehicles/
├── signals/
├── stations/
├── ui/
└── shared/
```

This directory usually contains:

- Vehicle definitions
- Signal logic
- Railway systems
- Gameplay mechanics
- Utility modules
- Shared libraries

`main.luatc` is generally used as the addon entry point.

## models/

The `models` directory contains every 3D model used by the addon.

```text title="Models directory"
models/
├── vehicles/
├── signals/
├── tracks/
├── stations/
└── props/
```

TransitCore supports multiple model formats depending on the installed model loaders.

Models are loaded through the Node system and can later be manipulated from LuaTC.

## textures/

Textures are stored separately from models.

```text title="Textures directory"
textures/
├── vehicles/
├── signals/
├── tracks/
├── ui/
└── misc/
```

Keeping textures organized by category simplifies maintenance as projects grow.

## animations/

Animations define moving parts of a model.

```text title="Animations directory"
animations/
├── doors/
├── cab/
├── pantographs/
├── bogies/
└── indicators/
```

Animations are associated with Nodes and controlled through LuaTC.

Typical animated elements include:

- Doors
- Buttons
- Switches
- Pantographs
- Windshield wipers
- Driver controls

## sounds/

Audio resources are stored inside the `sounds` directory.

```text title="Sounds directory"
sounds/
├── engines/
├── brakes/
├── doors/
├── announcements/
├── ambience/
└── ui/
```

TransitCore automatically loads supported sound files and makes them available through the audio service.

## lang/

The `lang` directory contains localization files.

```text title="Localization"
lang/
├── en_us.json
├── fr_fr.json
├── de_de.json
└── ja_jp.json
```

Every visible text should be localized whenever possible.

This allows the addon to support multiple languages without modifying LuaTC scripts.

## ui/

The `ui` directory contains graphical user interface resources.

```text title="UI directory"
ui/
├── icons/
├── images/
├── layouts/
└── themes/
```

User interface assets may include:

- Icons
- Menus
- Configuration panels
- Dashboard layouts
- Custom textures

## README.md

Although optional, every addon should include a README file.

```text title="Documentation"
README.md
```

The README can explain:

- The purpose of the addon
- Installation instructions
- Compatibility information
- Known limitations
- License
- Credits

A well-written README makes it easier for other developers to understand and contribute to the project.

## Recommended organization

As an addon becomes larger, grouping files by feature is recommended.

```text title="Large addon example"
scripts/
├── vehicles/
│   ├── metro/
│   ├── tram/
│   └── train/
├── railway/
├── signaling/
├── stations/
├── ui/
└── shared/
```

This approach improves readability and makes code reuse significantly easier.

<Alert severity="success">

Organize files by feature rather than placing everything inside a single directory. A consistent structure makes large addons easier to navigate and maintain.

</Alert>

## Files to avoid modifying

Some directories created by TransitCore are managed automatically.

For example:

```text title="TransitCore directories"
.minecraft/
├── TC_Cache/
├── TC_Logs/
└── TC_Config/
```

These directories should generally not be modified manually unless instructed by the documentation.

## Best practices

When organizing an addon:

- Keep related files together.
- Use descriptive file names.
- Separate reusable code into shared modules.
- Avoid duplicate resources.
- Follow a consistent naming convention.
- Keep the project structure identical across addons whenever possible.

A predictable directory layout benefits both developers and users.

## Next Steps

Now that you understand how addon files are organized, continue with **Your First Addon** to create a complete TransitCore addon from scratch.