---
title: Panoramica
description: Scopri cos'è TransitCore, come funziona e i principi che hanno guidato il suo sviluppo.
---

# Panoramica

Benvenuto in **TransitCore**.

TransitCore è un framework modulare di simulazione ferroviaria per Minecraft, progettato per creare reti ferroviarie realistiche grazie a un potente sistema di Addon e al linguaggio di scripting **LuaTC**.

A differenza delle tradizionali mod ferroviarie, TransitCore non include direttamente treni, metropolitane o infrastrutture. Il framework fornisce il motore di simulazione, mentre tutti i contenuti vengono distribuiti come Addon indipendenti.

<Alert severity="info">

TransitCore separa completamente il **motore** dai **contenuti**. Il framework fornisce i sistemi di simulazione, mentre gli Addon aggiungono veicoli, binari, segnali, stazioni, linee aeree e qualsiasi altro contenuto.

</Alert>

## Perché TransitCore?

TransitCore si basa su quattro principi fondamentali.

### Realismo

L'obiettivo di TransitCore è riprodurre i sistemi ferroviari nel modo più fedele possibile, mantenendo al tempo stesso una perfetta integrazione con Minecraft.

Il framework supporta, tra le altre cose:

- Simulazione avanzata dei veicoli.
- Sistemi frenanti realistici.
- Segnalamento ferroviario.
- Sistemi elettrici.
- Gestione di stazioni e passeggeri.
- Sincronizzazione multiplayer.
- Supporto per i treni ad alta velocità.

### Modularità

Ogni elemento di TransitCore è progettato per essere modulare.

Il framework contiene esclusivamente il motore di simulazione.

Veicoli, infrastrutture, suoni, texture, interfacce utente ed estensioni di gameplay vengono distribuiti come Addon installabili, aggiornabili e rimovibili in modo indipendente.

### Prestazioni

TransitCore è progettato per gestire in modo efficiente reti ferroviarie di grandi dimensioni.

Rendering, fisica, rete e simulazione sono ottimizzati per ridurre i calcoli non necessari mantenendo un comportamento realistico.

### Estensibilità

Tutte le funzionalità del framework sono accessibili tramite **LuaTC**, il linguaggio ufficiale di TransitCore.

Gli sviluppatori possono creare Addon completi senza modificare il codice Java del motore.

## Architettura

TransitCore è composto da diversi sistemi indipendenti che lavorano insieme.

```text title="Architettura di TransitCore"
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

Ogni sistema è responsabile di una parte specifica del framework e comunica con gli altri attraverso un'API pubblica e stabile.

## LuaTC

LuaTC è il linguaggio di scripting ufficiale di TransitCore.

Estende Lua con un'API progettata specificamente per la simulazione ferroviaria, consentendo agli sviluppatori di interagire con il framework senza accedere direttamente ai sistemi interni di Minecraft.

```luatc title="Creazione di un veicolo"
local train = tc.vehicle.create(tc.VehicleType.TRAIN)

train:setName("TGV Duplex")
train:setMaximumSpeed(320)
train:setMass(383000)
```

<Alert severity="success">

La maggior parte degli Addon può essere sviluppata interamente in LuaTC. Java è necessario solo quando si desidera estendere il motore di TransitCore.

</Alert>

## Addon

TransitCore utilizza un'architettura interamente basata sugli Addon.

Ogni Addon viene caricato in modo indipendente e comunica con il framework tramite LuaTC.

Gli Addon possono aggiungere:

- Treni.
- Metropolitane.
- Tram.
- Funicolari.
- Binari.
- Segnali.
- Linee aeree.
- Stazioni.
- Interfacce utente.
- Suoni.
- Estensioni di gameplay.

Se un Addon genera un errore durante il caricamento, TransitCore lo disabilita automaticamente senza impedire al framework o agli altri Addon di continuare a funzionare.

```text title="Struttura di un Addon"
MyAddon/
├── addon.yaml
├── scripts/
├── models/
├── textures/
├── sounds/
└── lang/
```

<Alert severity="warning" title="Isolamento degli Addon">

Un Addon difettoso non può impedire l'avvio di TransitCore. Il framework rileva automaticamente l'errore, disabilita soltanto l'Addon interessato e continua a caricare tutti gli altri.

</Alert>

## Documentazione

La documentazione è organizzata nelle seguenti sezioni.

| Sezione | Descrizione |
|---------|-------------|
| Getting Started | Installare TransitCore e creare il primo Addon. |
| LuaTC | Imparare il linguaggio di scripting ufficiale del framework. |
| Guides | Guide dettagliate dedicate a ogni sistema di TransitCore. |
| API Reference | Riferimento completo di servizi, classi, metodi ed eventi. |
| Examples | Progetti di esempio che illustrano le migliori pratiche. |

## Progetto Open Source

TransitCore è un progetto open source sviluppato da **Fire Sparks Studio**.

Il codice sorgente, la documentazione e il sistema di gestione delle segnalazioni sono pubblicamente disponibili, consentendo alla comunità di proporre miglioramenti, segnalare problemi e contribuire allo sviluppo del framework.

## Passaggio successivo

Se stai utilizzando TransitCore per la prima volta, continua con **Installation** per configurare l'ambiente di sviluppo e creare il tuo primo Addon.