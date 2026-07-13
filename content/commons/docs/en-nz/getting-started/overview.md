---
title: Overview
description: Learn what TransitCore is, how it works and the principles behind its design.
---

# Overview

Welcome to **TransitCore**.

TransitCore is a modular railway simulation framework for Minecraft, designed to build realistic railway networks through a powerful Addon system and the **LuaTC** scripting language.

Unlike traditional railway mods, TransitCore does not directly include trains, metros or infrastructure. The framework provides the simulation engine, while all content is distributed as independent Addons.

<Alert severity="info">

TransitCore completely separates the **engine** from the **content**. The framework provides the simulation systems, while Addons provide vehicles, tracks, signalling, stations, overhead catenary and every other railway asset.

</Alert>

## Why TransitCore?

TransitCore is built around four core principles.

### Realism

TransitCore aims to reproduce railway systems as accurately as possible while remaining fully integrated with Minecraft.

The framework supports:

- Advanced vehicle simulation.
- Realistic braking systems.
- Railway signalling.
- Electrical systems.
- Passenger and station operations.
- Multiplayer synchronisation.
- High-speed rail operations.

### Modularity

Everything in TransitCore is designed to be modular.

The framework itself contains only the simulation engine.

Vehicles, infrastructure, sounds, textures, user interfaces and gameplay extensions are distributed as independent Addons that can be installed, updated or removed separately.

### Performance

TransitCore is designed to efficiently handle large railway networks.

Rendering, physics, networking and simulation are optimised to minimise unnecessary calculations while maintaining realistic behaviour.

### Extensibility

All framework features are available through **LuaTC**, the official scripting language of TransitCore.

Developers can create complete Addons without modifying the Java engine.

## Architecture

TransitCore consists of multiple independent systems working together.

```text title="TransitCore Architecture"
TransitCore
├── Core Engine
├── Physics Engine
├── Rendering Engine
├── Railway Engine
├── Signalling Engine
├── Electrical Engine
├── Audio Engine
├── Animation Engine
├── Networking Engine
├── LuaTC Runtime
└── Addon Loader
```

Each system is responsible for a specific part of the framework and communicates through a stable public API.

## LuaTC

LuaTC is the official scripting language of TransitCore.

It extends Lua with APIs specifically designed for railway simulation, allowing developers to interact with the framework without accessing Minecraft internals.

```luatc title="Creating a Vehicle"
local train = tc.vehicle.create(tc.VehicleType.TRAIN)

train:setName("TGV Duplex")
train:setMaximumSpeed(320)
train:setMass(383000)
```

<Alert severity="success">

Most Addons can be developed entirely in LuaTC. Java is only required when extending the TransitCore engine itself.

</Alert>

## Addons

TransitCore uses a fully modular Addon architecture.

Each Addon is loaded independently and communicates with the framework through LuaTC.

Addons can introduce:

- Trains.
- Metros.
- Trams.
- Funiculars.
- Tracks.
- Signals.
- Overhead catenary.
- Stations.
- User interfaces.
- Sounds.
- Gameplay extensions.

If an Addon encounters an error during start-up, TransitCore automatically disables it without preventing the framework or other Addons from continuing to load.

```text title="Addon Structure"
MyAddon/
├── addon.yaml
├── scripts/
├── models/
├── textures/
├── sounds/
└── lang/
```

<Alert severity="warning" title="Addon Isolation">

A faulty Addon cannot prevent TransitCore from starting. The framework automatically detects the error, disables only the affected Addon and continues loading every remaining Addon.

</Alert>

## Documentation

The documentation is organised into several sections.

| Section | Description |
|---------|-------------|
| Getting Started | Install TransitCore and create your first Addon. |
| LuaTC | Learn the official scripting language of the framework. |
| Guides | Detailed guides covering every major TransitCore system. |
| API Reference | Complete reference for services, classes, methods and events. |
| Examples | Sample projects demonstrating recommended practices. |

## Open Source

TransitCore is an open-source project developed by **Fire Sparks Studio**.

The source code, documentation and issue tracker are publicly available, allowing the community to propose improvements, report issues and contribute to the development of the framework.

## Next Steps

If you're new to TransitCore, continue with **Installation** to set up your development environment and create your first Addon.