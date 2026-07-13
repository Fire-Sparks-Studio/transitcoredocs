---
title: Přehled
description: Zjistěte, co je TransitCore, jak funguje a jaké principy stojí za jeho návrhem.
---

# Přehled

Vítejte v **TransitCore**.

TransitCore je modulární framework pro simulaci železnice v Minecraftu, navržený pro vytváření realistických železničních sítí pomocí výkonného systému Addonů a skriptovacího jazyka **LuaTC**.

Na rozdíl od tradičních železničních modů TransitCore přímo neobsahuje vlaky, metro ani infrastrukturu. Framework poskytuje simulační jádro, zatímco veškerý obsah je distribuován jako samostatné Addony.

<Alert severity="info">

TransitCore zcela odděluje **engine** od **obsahu**. Framework poskytuje simulační systémy, zatímco Addony přidávají vozidla, koleje, návěstidla, stanice, trolejové vedení a další železniční prvky.

</Alert>

## Proč TransitCore?

TransitCore je postaven na čtyřech základních principech.

### Realismus

Cílem TransitCore je co nejvěrněji simulovat skutečné železniční systémy při zachování plné integrace s Minecraftem.

Framework podporuje například:

- Pokročilou simulaci vozidel.
- Realistické brzdové systémy.
- Železniční zabezpečovací zařízení.
- Elektrické systémy.
- Provoz stanic a cestujících.
- Synchronizaci pro multiplayer.
- Provoz vysokorychlostních vlaků.

### Modularita

Vše v TransitCore je navrženo modulárně.

Samotný framework obsahuje pouze simulační engine.

Vozidla, infrastruktura, zvuky, textury, uživatelské rozhraní i herní rozšíření jsou distribuovány jako samostatné Addony, které lze nezávisle instalovat, aktualizovat nebo odebrat.

### Výkon

TransitCore je navržen tak, aby efektivně zvládal rozsáhlé železniční sítě.

Vykreslování, fyzika, síťová komunikace i simulace jsou optimalizovány tak, aby minimalizovaly zbytečné výpočty při zachování realistického chování.

### Rozšiřitelnost

Všechny funkce frameworku jsou dostupné prostřednictvím **LuaTC**, oficiálního skriptovacího jazyka TransitCore.

Vývojáři mohou vytvářet plnohodnotné Addony bez úpravy Java kódu samotného enginu.

## Architektura

TransitCore se skládá z několika nezávislých systémů, které spolupracují.

```text title="Architektura TransitCore"
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

Každý systém odpovídá za konkrétní část frameworku a komunikuje prostřednictvím stabilního veřejného API.

## LuaTC

LuaTC je oficiální skriptovací jazyk TransitCore.

Rozšiřuje Lua o API navržené speciálně pro železniční simulaci a umožňuje vývojářům pracovat s frameworkem bez přímého přístupu k interním systémům Minecraftu.

```luatc title="Vytvoření vozidla"
local train = tc.vehicle.create(tc.VehicleType.TRAIN)

train:setName("TGV Duplex")
train:setMaximumSpeed(320)
train:setMass(383000)
```

<Alert severity="success">

Většinu Addonů lze vytvořit kompletně v LuaTC. Java je potřeba pouze při rozšiřování samotného jádra TransitCore.

</Alert>

## Addony

TransitCore využívá plně modulární architekturu Addonů.

Každý Addon se načítá samostatně a komunikuje s frameworkem prostřednictvím LuaTC.

Addony mohou přidávat například:

- Vlaky.
- Metro.
- Tramvaje.
- Lanové dráhy.
- Koleje.
- Návěstidla.
- Trolejové vedení.
- Stanice.
- Uživatelská rozhraní.
- Zvuky.
- Herní rozšíření.

Pokud během načítání Addonu dojde k chybě, TransitCore jej automaticky deaktivuje, aniž by zabránil spuštění frameworku nebo ostatních Addonů.

```text title="Struktura Addonu"
MyAddon/
├── addon.yaml
├── scripts/
├── models/
├── textures/
├── sounds/
└── lang/
```

<Alert severity="warning" title="Izolace Addonů">

Chybný Addon nemůže zabránit spuštění TransitCore. Framework automaticky rozpozná chybu, deaktivuje pouze problémový Addon a pokračuje v načítání všech ostatních.

</Alert>

## Dokumentace

Dokumentace je rozdělena do několika částí.

| Sekce | Popis |
|--------|-------|
| Getting Started | Instalace TransitCore a vytvoření prvního Addonu. |
| LuaTC | Seznámení s oficiálním skriptovacím jazykem frameworku. |
| Guides | Podrobné návody ke všem hlavním systémům TransitCore. |
| API Reference | Kompletní reference služeb, tříd, metod a událostí. |
| Examples | Ukázkové projekty demonstrující doporučené postupy. |

## Open Source

TransitCore je open-source projekt vyvíjený společností **Fire Sparks Studio**.

Zdrojový kód, dokumentace i systém pro hlášení chyb jsou veřejně dostupné, takže komunita může navrhovat vylepšení, hlásit chyby a podílet se na vývoji frameworku.

## Další krok

Pokud s TransitCore začínáte, pokračujte na stránku **Installation**, kde nastavíte své vývojové prostředí a vytvoříte svůj první Addon.