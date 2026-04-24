# 🧬 Evolver

[![GitHub stars](https://img.shields.io/github/stars/EvoMap/evolver?style=social)](https://github.com/EvoMap/evolver/stargazers)
[![License: GPL-3.0](https://img.shields.io/badge/License-GPL--3.0-blue.svg)](https://opensource.org/licenses/GPL-3.0)
[![Node.js >= 18](https://img.shields.io/badge/Node.js-%3E%3D%2018-green.svg)](https://nodejs.org/)
[![GitHub last commit](https://img.shields.io/github/last-commit/EvoMap/evolver)](https://github.com/EvoMap/evolver/commits/main)
[![GitHub issues](https://img.shields.io/github/issues/EvoMap/evolver)](https://github.com/EvoMap/evolver/issues)

![Evolver Cover](assets/cover.png)

**[evomap.ai](https://evomap.ai)** | [ドキュメント](https://evomap.ai/wiki) | [English](README.md) | [中文文档](README.zh-CN.md) | [한국어 문서](README.ko-KR.md) | [GitHub](https://github.com/EvoMap/evolver) | [リリース](https://github.com/EvoMap/evolver/releases)

---

> **お知らせ — ソースアベイラブルへの移行**
>
> Evolver は 2026-02-01 の初回リリース以来、完全にオープンソースで公開されてきました（当初は MIT、2026-04-09 以降は GPL-3.0-or-later）。2026年3月、同じ領域の別プロジェクトが、Evolver へのいかなる帰属表示もなく、メモリ・スキル・進化アセットの設計が驚くほど類似したシステムをリリースしました。詳細な分析: [Hermes Agent Self-Evolution vs. Evolver: A Detailed Similarity Analysis](https://evomap.ai/en/blog/hermes-agent-evolver-similarity-analysis)。
>
> 作品の完全性を守り、この方向性に投資を続けるため、今後の Evolver リリースは完全なオープンソースからソースアベイラブルへ移行します。**ユーザーへのコミットメントは変わりません**: 業界で最良のエージェント自己進化機能を引き続き提供します — より速いイテレーション、より深い GEP 統合、より強力なメモリとスキルシステム。既に公開された MIT および GPL-3.0 バージョンは、元の条件のもとで引き続き自由に利用できます。`npm install @evomap/evolver` や本リポジトリのクローンは引き続き可能で、現在のワークフローは何も壊れません。
>
> 質問や懸念: issue を開くか、[evomap.ai](https://evomap.ai) までお問い合わせください。

---

> **「進化は任意ではない。適応するか、滅びるか。」**

**3行で説明**
- **何であるか**: AIエージェントのための[GEP](https://evomap.ai/wiki)駆動の自己進化エンジン。
- **解決する課題**: その場限りのプロンプト調整を、監査可能で再利用可能な進化アセットに変換する。
- **30秒で使い始める**: クローンし、インストールして、`evolver` を実行 -- GEPガイド付きの進化プロンプトを取得。

## EvoMap -- 進化ネットワーク

Evolverは **[EvoMap](https://evomap.ai)** のコアエンジンです。EvoMapは、AIエージェントが検証済みのコラボレーションを通じて進化するネットワークです。[evomap.ai](https://evomap.ai)にアクセスして、完全なプラットフォーム -- ライブエージェントマップ、進化リーダーボード、個別のプロンプト調整を共有可能で監査可能なインテリジェンスに変えるエコシステム -- をご覧ください。

キーワード: プロトコル制約付き進化、監査証跡、遺伝子とカプセル、プロンプトガバナンス。


## インストールパスの選び方

Evolver のインストール方法は 1 つですが、使い方は 2 種類あります。まず自分がどちらかを決め、該当するセクションだけ読んでください。

| パス | 対象読者 | インストール後のコマンド | ガイド |
|---|---|---|---|
| **CLI クイックスタート** | Evolver を使って Agent/プロジェクトを進化させたいだけの方。読者の 99% はこちらです。 | `evolver` | [下記](#cli-クイックスタート) |
| **ソースから実行** | エンジン本体を触る、PR を投げる、未リリース版を試したい貢献者向け。 | `node index.js` | [下記](#ソースから実行貢献者向け) |

> **Agent / Skill 連携** (Codex、Claude Code の skill システム、カスタム MCP クライアント) は別ドキュメント [SKILL.md](SKILL.md) を参照してください。そこでは CLI をラップする Proxy mailbox API を解説しています。まずは下記 CLI クイックスタートで Evolver をインストールしておく必要があります。

## インストール

### 前提条件

- **[Node.js](https://nodejs.org/)** >= 18
- **[Git](https://git-scm.com/)** -- 必須。Evolverはロールバック、影響範囲の算出、solidifyにgitを使用します。git管理外のディレクトリで実行すると、明確なエラーメッセージが表示されます。

> **個人メモ**: Node.js 20 LTS での動作確認済み。18 でも動くが、20 の方が体感的に安定している印象。

### npm からインストール（推奨）

```bash
npm install -g @evomap/evolver
```

`evolver` CLI がグローバルにインストールされます。`evolver --he
