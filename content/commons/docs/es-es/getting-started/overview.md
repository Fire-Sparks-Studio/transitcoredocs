---
title: Descripción general
description: Descubre qué es TransitCore, cómo funciona y los principios que guiaron su diseño.
---

# Descripción general

Bienvenido a **TransitCore**.

TransitCore es un framework modular de simulación ferroviaria para Minecraft, diseñado para crear redes ferroviarias realistas mediante un potente sistema de Addons y el lenguaje de scripting **LuaTC**.

A diferencia de los mods ferroviarios tradicionales, TransitCore no incluye directamente trenes, metros ni infraestructura. El framework proporciona el motor de simulación, mientras que todo el contenido se distribuye como Addons independientes.

<Alert severity="info">

TransitCore separa completamente el **motor** del **contenido**. El framework proporciona los sistemas de simulación, mientras que los Addons añaden vehículos, vías, señales, estaciones, catenarias y cualquier otro tipo de contenido.

</Alert>

## ¿Por qué TransitCore?

TransitCore se basa en cuatro principios fundamentales.

### Realismo

El objetivo de TransitCore es reproducir los sistemas ferroviarios con la mayor fidelidad posible, manteniendo al mismo tiempo una integración perfecta con Minecraft.

El framework incluye, entre otras características:

- Simulación avanzada de vehículos.
- Sistemas de frenado realistas.
- Señalización ferroviaria.
- Sistemas eléctricos.
- Operación de estaciones y pasajeros.
- Sincronización multijugador.
- Soporte para trenes de alta velocidad.

### Modularidad

Todo en TransitCore ha sido diseñado para ser modular.

El framework únicamente contiene el motor de simulación.

Los vehículos, las infraestructuras, los sonidos, las texturas, las interfaces de usuario y las extensiones de jugabilidad se distribuyen como Addons que pueden instalarse, actualizarse o eliminarse de forma independiente.

### Rendimiento

TransitCore está diseñado para gestionar de forma eficiente redes ferroviarias de gran tamaño.

El renderizado, la física, la red y la simulación están optimizados para reducir cálculos innecesarios sin sacrificar el realismo.

### Extensibilidad

Todas las funcionalidades del framework están disponibles mediante **LuaTC**, el lenguaje oficial de TransitCore.

Los desarrolladores pueden crear Addons completos sin modificar el código Java del motor.

## Arquitectura

TransitCore está compuesto por varios sistemas independientes que trabajan conjuntamente.

```text title="Arquitectura de TransitCore"
TransitCore
├── Core Engine
├── Physics Engine
├── Rendering Engine
├── Railway Engine
├── Signaling Engine
├── Electrical Engine
├── Audio Engine
├── Animation Engine
├── Networking Engine
├── LuaTC Runtime
└── Addon Loader
```

Cada sistema es responsable de una parte específica del framework y se comunica con los demás mediante una API pública y estable.

## LuaTC

LuaTC es el lenguaje oficial de scripting de TransitCore.

Amplía Lua con una API diseñada específicamente para la simulación ferroviaria, permitiendo a los desarrolladores interactuar con el framework sin acceder directamente a los sistemas internos de Minecraft.

```luatc title="Crear un vehículo"
local train = tc.vehicle.create(tc.VehicleType.TRAIN)

train:setName("TGV Duplex")
train:setMaximumSpeed(320)
train:setMass(383000)
```

<Alert severity="success">

La mayoría de los Addons pueden desarrollarse completamente en LuaTC. Solo es necesario utilizar Java cuando se desea ampliar el propio motor de TransitCore.

</Alert>

## Addons

TransitCore utiliza una arquitectura completamente basada en Addons.

Cada Addon se carga de forma independiente y se comunica con el framework mediante LuaTC.

Los Addons pueden añadir, entre otros:

- Trenes.
- Metros.
- Tranvías.
- Funiculares.
- Vías.
- Señales.
- Catenarias.
- Estaciones.
- Interfaces de usuario.
- Sonidos.
- Extensiones de jugabilidad.

Si un Addon encuentra un error durante su carga, TransitCore lo desactiva automáticamente sin impedir que el framework o los demás Addons continúen funcionando.

```text title="Estructura de un Addon"
MyAddon/
├── addon.yaml
├── scripts/
├── models/
├── textures/
├── sounds/
└── lang/
```

<Alert severity="warning" title="Aislamiento de Addons">

Un Addon defectuoso no puede impedir que TransitCore se inicie. El framework detecta automáticamente el error, desactiva únicamente el Addon afectado y continúa cargando el resto de los Addons.

</Alert>

## Documentación

La documentación está organizada en varias secciones.

| Sección | Descripción |
|---------|-------------|
| Getting Started | Instalar TransitCore y crear tu primer Addon. |
| LuaTC | Aprender el lenguaje oficial de scripting del framework. |
| Guides | Tutoriales detallados sobre cada sistema de TransitCore. |
| API Reference | Referencia completa de servicios, clases, métodos y eventos. |
| Examples | Proyectos de ejemplo que muestran las mejores prácticas. |

## Proyecto de código abierto

TransitCore es un proyecto de código abierto desarrollado por **Fire Sparks Studio**.

El código fuente, la documentación y el sistema de seguimiento de incidencias están disponibles públicamente para que la comunidad pueda proponer mejoras, informar de errores y contribuir al desarrollo del framework.

## Siguiente paso

Si es la primera vez que utilizas TransitCore, continúa con **Installation** para configurar tu entorno de desarrollo y crear tu primer Addon.