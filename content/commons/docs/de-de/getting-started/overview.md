---
title: Übersicht
description: Erfahren Sie, was TransitCore ist, wie es funktioniert und welche Grundprinzipien hinter seiner Entwicklung stehen.
---

# Übersicht

Willkommen bei **TransitCore**.

TransitCore ist ein modulares Eisenbahnsimulations-Framework für Minecraft, das die Erstellung realistischer Schienennetze mithilfe eines leistungsfähigen Addon-Systems und der Skriptsprache **LuaTC** ermöglicht.

Im Gegensatz zu herkömmlichen Eisenbahn-Mods enthält TransitCore keine Züge, U-Bahnen oder Infrastruktur. Das Framework stellt die Simulations-Engine bereit, während sämtliche Inhalte als unabhängige Addons verteilt werden.

<Alert severity="info">

TransitCore trennt die **Engine** vollständig vom **Inhalt**. Das Framework stellt die Simulationssysteme bereit, während Addons Fahrzeuge, Gleise, Signale, Bahnhöfe, Oberleitungen und alle weiteren Eisenbahnelemente hinzufügen.

</Alert>

## Warum TransitCore?

TransitCore basiert auf vier grundlegenden Prinzipien.

### Realismus

TransitCore verfolgt das Ziel, Eisenbahnsysteme möglichst realitätsgetreu nachzubilden und gleichzeitig eine nahtlose Integration in Minecraft zu gewährleisten.

Das Framework unterstützt unter anderem:

- Erweiterte Fahrzeugsimulation.
- Realistische Bremssysteme.
- Eisenbahnsignalisierung.
- Elektrische Systeme.
- Fahrgast- und Bahnhofsmanagement.
- Multiplayer-Synchronisation.
- Hochgeschwindigkeitsverkehr.

### Modularität

Alle Bestandteile von TransitCore sind modular aufgebaut.

Das Framework selbst enthält ausschließlich die Simulations-Engine.

Fahrzeuge, Infrastruktur, Sounds, Texturen, Benutzeroberflächen und Gameplay-Erweiterungen werden als unabhängige Addons bereitgestellt, die separat installiert, aktualisiert oder entfernt werden können.

### Leistung

TransitCore wurde entwickelt, um auch große Eisenbahnnetze effizient zu verwalten.

Rendering, Physik, Netzwerk und Simulation sind optimiert, um unnötige Berechnungen zu minimieren und gleichzeitig ein realistisches Verhalten zu gewährleisten.

### Erweiterbarkeit

Alle Funktionen des Frameworks stehen über **LuaTC**, die offizielle Skriptsprache von TransitCore, zur Verfügung.

Entwickler können vollständige Addons erstellen, ohne den Java-Code der Engine ändern zu müssen.

## Architektur

TransitCore besteht aus mehreren unabhängigen Systemen, die zusammenarbeiten.

```text title="TransitCore-Architektur"
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

Jedes System ist für einen bestimmten Teil des Frameworks verantwortlich und kommuniziert über eine stabile öffentliche API mit den anderen Systemen.

## LuaTC

LuaTC ist die offizielle Skriptsprache von TransitCore.

Sie erweitert Lua um APIs, die speziell für die Eisenbahnsimulation entwickelt wurden, sodass Entwickler mit dem Framework arbeiten können, ohne direkt auf die internen Systeme von Minecraft zugreifen zu müssen.

```luatc title="Ein Fahrzeug erstellen"
local train = tc.vehicle.create(tc.VehicleType.TRAIN)

train:setName("TGV Duplex")
train:setMaximumSpeed(320)
train:setMass(383000)
```

<Alert severity="success">

Die meisten Addons können vollständig in LuaTC entwickelt werden. Java wird nur benötigt, wenn die TransitCore-Engine selbst erweitert werden soll.

</Alert>

## Addons

TransitCore verwendet eine vollständig modulare Addon-Architektur.

Jedes Addon wird unabhängig geladen und kommuniziert über LuaTC mit dem Framework.

Addons können beispielsweise Folgendes hinzufügen:

- Züge.
- U-Bahnen.
- Straßenbahnen.
- Standseilbahnen.
- Gleise.
- Signale.
- Oberleitungen.
- Bahnhöfe.
- Benutzeroberflächen.
- Sounds.
- Gameplay-Erweiterungen.

Tritt beim Laden eines Addons ein Fehler auf, deaktiviert TransitCore dieses automatisch, ohne das Framework oder andere Addons am Start zu hindern.

```text title="Addon-Struktur"
MyAddon/
├── addon.yaml
├── scripts/
├── models/
├── textures/
├── sounds/
└── lang/
```

<Alert severity="warning" title="Addon-Isolierung">

Ein fehlerhaftes Addon kann den Start von TransitCore nicht verhindern. Das Framework erkennt den Fehler automatisch, deaktiviert nur das betroffene Addon und lädt alle übrigen Addons weiterhin.

</Alert>

## Dokumentation

Die Dokumentation ist in mehrere Bereiche gegliedert.

| Abschnitt | Beschreibung |
|-----------|--------------|
| Getting Started | TransitCore installieren und das erste Addon erstellen. |
| LuaTC | Die offizielle Skriptsprache des Frameworks kennenlernen. |
| Guides | Detaillierte Anleitungen zu allen wichtigen Systemen von TransitCore. |
| API Reference | Vollständige Referenz zu Services, Klassen, Methoden und Ereignissen. |
| Examples | Beispielprojekte mit empfohlenen Vorgehensweisen. |

## Open Source

TransitCore ist ein Open-Source-Projekt von **Fire Sparks Studio**.

Der Quellcode, die Dokumentation und der Issue-Tracker sind öffentlich verfügbar, sodass die Community Verbesserungen vorschlagen, Fehler melden und zur Weiterentwicklung des Frameworks beitragen kann.

## Nächste Schritte

Wenn Sie TransitCore zum ersten Mal verwenden, fahren Sie mit **Installation** fort, um Ihre Entwicklungsumgebung einzurichten und Ihr erstes Addon zu erstellen.