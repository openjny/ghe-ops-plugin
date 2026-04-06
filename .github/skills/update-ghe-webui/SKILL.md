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
- Settings ページだけでなく、設定に相当する操作ができるすべてのトップナビ項目（Security and quality、Insights 等）も対象とする
- 各 reference ファイル内で、サイドナビ・タブのすべてのサブページが記録されている
- 各サブページ内の設定項目・機能がすべてリスト化されている（パスだけの記録は不十分。「何ができるか」まで記録する）
- UI から消えた項目が残っていない

### 2. 逆引き可能性

- 「○○の設定はどこにあるか？」という問いに reference から回答できること
- すべてのサブページについて「パス + そこで何ができるか」がセットで記録されていること
- ナビゲーションテーブルにパスだけ記載してセクションの中身が空、という状態は品質基準を満たさない

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
- `ghe-webui` の SKILL.md では URL パターンテーブルと references リンクを統合する（同じテーブル内に reference ファイルへのリンクを含める）

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
2. **発見**: トップナビの全項目を読み取る。Settings 以外にも設定に相当するページ（Security and quality、Insights 等）があるため、すべてのトップナビ項目を対象とする
3. **深掘り**: 各トップナビ項目に遷移し、サイドナビ・タブを発見。さらに各サブページに遷移して「何ができるか」を収集する。パスの記録だけで終わらせない
4. **補強**: 新規・不明な設定項目は GitHub Docs で概念を確認し、脚注を付与する
5. **反映**: reference ファイルと SKILL.md を更新する。SKILL.md の URL テーブルには reference ファイルへのリンクを含める

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

## 良い例・悪い例

### 悪い例: パスだけで中身がない

```markdown
### Code and automation

| 項目 | パス |
|------|------|
| Branches | `/{owner}/{repo}/settings/branches` |
| Webhooks | `/{owner}/{repo}/settings/hooks` |
| Environments | `/{owner}/{repo}/settings/environments` |
```

→ 「Branches で何ができるか」がわからない。逆引きできない。

### 良い例: 何ができるかまで書いてある

```markdown
### Code and automation

#### Branches

> パス: `/{owner}/{repo}/settings/branches`

- デフォルトブランチの変更
- ブランチ保護ルールの作成・編集（レビュー必須、ステータスチェック、force push 禁止等）[^2]

#### Webhooks

> パス: `/{owner}/{repo}/settings/hooks`

- Webhook の追加・編集・削除
- イベントの選択（push, PR, issues 等）と配信先 URL の設定
- 最近の配信履歴の確認・再送

#### Environments

> パス: `/{owner}/{repo}/settings/environments`

- デプロイ環境の作成・管理
- 環境保護ルール（レビュアー指定、待機時間）の設定
- 環境固有の Secrets と Variables の管理[^3]
```

→ 「ブランチ保護ルールはどこで設定する？」→ 「Branches」と逆引きできる。

### 悪い例: UI 実装詳細が細かすぎる

```markdown
#### General

| 項目 | 説明 | 入力タイプ |
|------|------|-----------|
| Enterprise display name | 表示名（必須） | テキスト |
| Description | 説明（任意） | テキスト |
| Website URL | Web サイト URL（任意） | テキスト |
| Location | 所在地（任意） | テキスト |
```

→ 入力タイプやテーブルの列構造は不要。

### 良い例: 適切な粒度

```markdown
#### General

- Enterprise の表示名、説明、Web サイト URL、所在地、セキュリティ連絡先メールを設定できる
- プロフィール画像をアップロードできる
- Profile name visibility: メンバーのプロフィール名をハンドルと一緒に表示するか（Let organizations decide / Enabled / Disabled）
```

→ 何が設定できるかが分かる。ポリシー選択肢は記録する。入力タイプは省略。

## SKILL.md テンプレート

`ghe-webui/SKILL.md` の URL パターンテーブルは reference ファイルへのリンクを統合する。

```markdown
### {レベル名} レベル

ベースパス: `/{base-path}`

| ページ | パス | 備考 | Reference |
|--------|------|------|-----------|
| {ページ名} | `/{path}` | {備考} | [詳細](./references/{file}.md) |
| ... | ... | ... | ... |
```

---

[^1]: [GitHub Enterprise Cloud documentation](https://docs.github.com/enterprise-cloud@latest)
