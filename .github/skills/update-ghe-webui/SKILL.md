---
name: update-ghe-webui
description: "ghe-webui スキルの references を最新の GitHub Enterprise UI に合わせて更新するメンテナンススキル。Use when: ghe-webui の内容を最新化したい、新しい GHE 機能の UI 情報を記録したい、UI 変更の差分を検出したい。Triggers: ghe-webui 更新, UI 情報更新, GHE UI スキャン, references メンテナンス"
argument-hint: "更新対象 (例: 全体スキャン, enterprise-ai-controls のみ)"
user-invocable: true
---

# update-ghe-webui — GHE Web UI 知識ベースの更新

`ghe-webui` スキルの references/ 配下のファイルを、実際の GitHub Enterprise UI と照合して更新する。

## ゴール

`ghe-webui` の references が以下の品質基準をすべて満たしている状態にすること。

## 品質基準

### 1. 網羅性

- 実際の UI に存在するすべてのトップナビ項目に対応する reference ファイルが存在する
- 各 reference ファイル内で、サイドナビ・タブのすべてのサブページが記録されている
- 各サブページ内の設定項目・機能がすべてリスト化されている
- UI から消えた項目が残っていない

### 2. 正確性

- ナビゲーション項目名が実際の UI と一致している
- URL パスが実際のパスと一致している
- ポリシー選択肢（Enabled/Disabled/Let organizations decide 等）が正確
- 環境固有の値（ホスト名、Org 名、ユーザー名、具体的な数値）を含まない

### 3. 適切な粒度

- 各設定について「何ができるか」が分かる（例: 「Enterprise の表示名・説明・所在地を設定できる」）
- ポリシー選択肢は記録する（ナビゲーション判断に必要なため）
- 入力フィールドの型・個数・バリデーション等の UI 実装詳細は記録しない
- UI 要素（ボタン名・検索ボックスの有無等）は、ナビゲーションに必要な場合のみ記録する

### 4. 概念の裏付け

- 各設定項目が何を意味し、何に影響するかが GitHub Docs の脚注[^1]で裏付けられている
- 脚注 URL は docs.github.com の有効なパスであること

### 5. 構造の一貫性

- ファイル命名規則: `enterprise-{nav-item}.md`, `org-{nav-item}.md`, `repo-{nav-item}.md`
- 各ファイルは「概要 → ナビゲーション → セクション別の設定リスト → 脚注」の構造を持つ
- `ghe-webui` の SKILL.md の URL パターンテーブルと references リンクが最新

## 終了条件

- 対象スコープ（全体 / 特定セクション）内のすべての reference ファイルが品質基準を満たしている
- `ghe-webui/SKILL.md` の URL パターンテーブルと references リンクが最新
- 更新サマリー（追加・変更・削除された項目）をユーザーに報告済み

## 制約

- `ghe-webui` の knowledge base を更新するのみ。GHE の設定自体は変更しない
- ブラウザ操作は `clickops` スキルの安全ガイドラインに従う（読み取り専用）
- 巡回先は固定リストではなく、実際の UI ナビゲーションから動的に発見する
- `clickops` で対象ページにアクセスし、GitHub Docs で概念を補強する

## 巡回の方針

1. **起点**: Enterprise / Org / Repo のトップページを開く
2. **発見**: トップナビの全項目を読み取り、既存 references との差分を確認する
3. **深掘り**: 各トップナビ項目に遷移し、サイドナビ・タブを発見。さらに各サブページに遷移して設定項目を収集する
4. **補強**: 新規・不明な設定項目は GitHub Docs で概念を確認し、脚注を付与する
5. **反映**: reference ファイルと SKILL.md を更新する

## reference ファイルテンプレート

```markdown
# {ページ名}

> パス: `/{path}`

## 概要

{ページの目的・機能を 1-3 行で}

## ナビゲーション

| 項目 | パス |
|------|------|
| ... | ... |

## セクション: {セクション名}

{どんな設定・操作ができるかのリスト}

- 設定 A: {説明}（選択肢: X / Y / Z）
- 設定 B: {説明}

---

[^1]: [GitHub Docs: {topic}](https://docs.github.com/...)
```

---

[^1]: [GitHub Enterprise Cloud documentation](https://docs.github.com/enterprise-cloud@latest)
