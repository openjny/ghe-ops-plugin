# Enterprise Compliance

> パス: `/enterprises/{enterprise}/settings/compliance`

## 概要

コンプライアンスレポートの管理。コンプライアンス認証レポートのダウンロードと、Dormant Users レポートの生成を行う。

## ナビゲーション

サブナビゲーションなし（単一ページ）。

## Resources

> パス: `/enterprises/{enterprise}/settings/compliance`

コンプライアンスレポート（SOC 2、ISO 27001 等）のダウンロード。利用可能なレポートがない場合は「No compliance reports」と表示される。

## Reports

> パス: `/enterprises/{enterprise}/settings/compliance`

### Dormant Users

30日間非アクティブな Organization メンバーおよび外部コラボレーターのレポート。[^1]

- アクションボタン: 「New report」（新規 Dormant Users レポートの生成）

---

[^1]: [GitHub Docs: Managing dormant users](https://docs.github.com/admin/managing-accounts-and-repositories/managing-users-in-your-enterprise/managing-dormant-users)
