---
title: Visão Geral
description: Descubra o que é o TransitCore, como funciona e os princípios que orientam o seu desenvolvimento.
---

# Visão Geral

Bem-vindo ao **TransitCore**.

O TransitCore é um framework modular de simulação ferroviária para Minecraft, desenvolvido para criar redes ferroviárias realistas através de um poderoso sistema de Addons e da linguagem de scripting **LuaTC**.

Ao contrário dos mods ferroviários tradicionais, o TransitCore não inclui diretamente comboios, metros ou infraestruturas. O framework fornece o motor de simulação, enquanto todo o conteúdo é distribuído como Addons independentes.

<Alert severity="info">

O TransitCore separa completamente o **motor** do **conteúdo**. O framework fornece os sistemas de simulação, enquanto os Addons adicionam veículos, vias, sinais, estações, catenárias e qualquer outro elemento ferroviário.

</Alert>

## Porquê o TransitCore?

O TransitCore foi desenvolvido com base em quatro princípios fundamentais.

### Realismo

O objetivo do TransitCore é reproduzir sistemas ferroviários da forma mais fiel possível, mantendo uma integração perfeita com o Minecraft.

O framework suporta:

- Simulação avançada de veículos.
- Sistemas de travagem realistas.
- Sinalização ferroviária.
- Sistemas elétricos.
- Operação de estações e passageiros.
- Sincronização multijogador.
- Operação de comboios de alta velocidade.

### Modularidade

Tudo no TransitCore foi concebido para ser modular.

O próprio framework contém apenas o motor de simulação.

Veículos, infraestruturas, sons, texturas, interfaces de utilizador e extensões de jogabilidade são distribuídos como Addons independentes, podendo ser instalados, atualizados ou removidos separadamente.

### Desempenho

O TransitCore foi desenvolvido para gerir eficientemente grandes redes ferroviárias.

O rendering, a física, a rede e a simulação são otimizados para reduzir cálculos desnecessários, mantendo um comportamento realista.

### Extensibilidade

Todas as funcionalidades do framework estão disponíveis através do **LuaTC**, a linguagem oficial de scripting do TransitCore.

Os programadores podem criar Addons completos sem modificar o código Java do motor.

## Arquitetura

O TransitCore é composto por vários sistemas independentes que trabalham em conjunto.

```text title="Arquitetura do TransitCore"
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

Cada sistema é responsável por uma parte específica do framework e comunica através de uma API pública e estável.

## LuaTC

O LuaTC é a linguagem oficial de scripting do TransitCore.

Expande a linguagem Lua com APIs especificamente concebidas para a simulação ferroviária, permitindo aos programadores interagir com o framework sem aceder diretamente aos sistemas internos do Minecraft.

```luatc title="Criar um veículo"
local train = tc.vehicle.create(tc.VehicleType.TRAIN)

train:setName("TGV Duplex")
train:setMaximumSpeed(320)
train:setMass(383000)
```

<Alert severity="success">

A maioria dos Addons pode ser desenvolvida inteiramente em LuaTC. O Java só é necessário quando se pretende expandir o próprio motor do TransitCore.

</Alert>

## Addons

O TransitCore utiliza uma arquitetura totalmente baseada em Addons.

Cada Addon é carregado de forma independente e comunica com o framework através do LuaTC.

Os Addons podem adicionar:

- Comboios.
- Metros.
- Elétricos.
- Funiculares.
- Vias.
- Sinais.
- Catenárias.
- Estações.
- Interfaces de utilizador.
- Sons.
- Extensões de jogabilidade.

Se um Addon encontrar um erro durante o arranque, o TransitCore desativa-o automaticamente sem impedir que o framework ou os restantes Addons continuem a ser carregados.

```text title="Estrutura de um Addon"
MyAddon/
├── addon.yaml
├── scripts/
├── models/
├── textures/
├── sounds/
└── lang/
```

<Alert severity="warning" title="Isolamento dos Addons">

Um Addon com erros não pode impedir o arranque do TransitCore. O framework deteta automaticamente o erro, desativa apenas o Addon afetado e continua a carregar todos os restantes.

</Alert>

## Documentação

A documentação está organizada em várias secções.

| Secção | Descrição |
|--------|-----------|
| Getting Started | Instalar o TransitCore e criar o primeiro Addon. |
| LuaTC | Aprender a linguagem oficial de scripting do framework. |
| Guides | Guias detalhados sobre todos os principais sistemas do TransitCore. |
| API Reference | Referência completa de serviços, classes, métodos e eventos. |
| Examples | Projetos de exemplo que demonstram as melhores práticas. |

## Código Aberto

O TransitCore é um projeto de código aberto desenvolvido pela **Fire Sparks Studio**.

O código-fonte, a documentação e o sistema de gestão de problemas estão disponíveis publicamente, permitindo que a comunidade proponha melhorias, reporte erros e contribua para o desenvolvimento do framework.

## Próximo Passo

Se esta é a sua primeira utilização do TransitCore, continue para **Installation** para configurar o ambiente de desenvolvimento e criar o seu primeiro Addon.