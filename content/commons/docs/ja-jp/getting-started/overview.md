---
title: 概要
description: TransitCoreとは何か、その仕組みと設計理念について説明します。
---

# 概要

**TransitCore** へようこそ。

TransitCore は、Minecraft 向けに開発されたモジュール式の鉄道シミュレーションフレームワークです。強力なアドオンシステムと **LuaTC** スクリプト言語を使用して、リアルな鉄道ネットワークを構築できます。

従来の鉄道 MOD とは異なり、TransitCore 自体には車両や鉄道設備は含まれていません。フレームワークはシミュレーションエンジンのみを提供し、車両やインフラなどのコンテンツは独立した Addon として提供されます。

<Alert severity="info">

TransitCore は **エンジン** と **コンテンツ** を完全に分離しています。フレームワークはシミュレーションシステムを提供し、Addon が車両、線路、信号機、駅、架線などのコンテンツを追加します。

</Alert>

## TransitCore を選ぶ理由

TransitCore は、4つの基本理念に基づいて設計されています。

### リアリズム

TransitCore の目的は、Minecraft の世界に自然に統合しながら、現実の鉄道システムをできる限り忠実に再現することです。

主な機能：

- 高度な車両シミュレーション
- リアルなブレーキシステム
- 本格的な鉄道信号システム
- 電力供給システム
- 旅客運行シミュレーション
- マルチプレイヤー同期
- 高速鉄道への対応

### モジュール設計

TransitCore のすべての機能はモジュール化されています。

フレームワーク本体にはシミュレーションエンジンのみが含まれます。

車両、インフラ、サウンド、テクスチャ、ユーザーインターフェース、ゲームプレイ機能は、それぞれ独立した Addon として配布され、個別にインストール、更新、削除できます。

### パフォーマンス

TransitCore は、大規模な鉄道ネットワークでも効率よく動作するよう設計されています。

描画、物理演算、ネットワーク通信、シミュレーションは最適化されており、不要な処理を最小限に抑えながら、高い精度を維持します。

### 拡張性

TransitCore のすべての主要機能は **LuaTC** を通じて利用できます。

開発者は Java のコードを変更することなく、完全な Addon を作成できます。

## アーキテクチャ

TransitCore は、複数の独立したシステムで構成されています。

```text title="TransitCore アーキテクチャ"
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

各システムは特定の役割を担当し、安定した公開 API を通じて相互に連携します。

## LuaTC

LuaTC は TransitCore の公式スクリプト言語です。

Lua を拡張し、鉄道シミュレーション専用の API を提供します。Minecraft の内部システムを直接操作することなく、TransitCore の機能を利用できます。

```luatc title="車両の作成"
local train = tc.vehicle.create(tc.VehicleType.TRAIN)

train:setName("TGV Duplex")
train:setMaximumSpeed(320)
train:setMass(383000)
```

<Alert severity="success">

ほとんどの Addon は LuaTC のみで開発できます。Java が必要になるのは、TransitCore のコアエンジン自体を拡張する場合のみです。

</Alert>

## Addon

TransitCore は Addon ベースのアーキテクチャを採用しています。

各 Addon は独立して読み込まれ、LuaTC を通じてフレームワークと連携します。

Addon では以下のようなコンテンツを追加できます。

- 列車
- 地下鉄
- 路面電車
- ケーブルカー
- 線路
- 信号機
- 架線
- 駅
- ユーザーインターフェース
- サウンド
- ゲームプレイ拡張

Addon の読み込み中にエラーが発生した場合でも、TransitCore はその Addon のみを無効化し、他の Addon の読み込みを継続します。

```text title="Addon 構成例"
MyAddon/
├── addon.yaml
├── scripts/
├── models/
├── textures/
├── sounds/
└── lang/
```

<Alert severity="warning" title="Addon の分離">

不具合のある Addon が TransitCore 全体の起動を妨げることはありません。問題のある Addon のみが無効化され、他の Addon は通常どおり読み込まれます。

</Alert>

## ドキュメント構成

ドキュメントは以下のセクションに分かれています。

| セクション | 内容 |
|------------|------|
| Getting Started | TransitCore のインストールと最初の Addon の作成方法 |
| LuaTC | LuaTC スクリプト言語の解説 |
| Guides | 各システムの詳細なチュートリアル |
| API Reference | サービス、クラス、メソッド、イベントの完全なリファレンス |
| Examples | 実践的なサンプルプロジェクト |

## オープンソース

TransitCore は **Fire Sparks Studio** が開発するオープンソースプロジェクトです。

ソースコード、ドキュメント、Issue Tracker は公開されており、誰でも改善提案やバグ報告、開発への参加が可能です。

## 次のステップ

TransitCore を初めて利用する場合は、**Installation** に進み、開発環境を構築して最初の Addon を作成してください。