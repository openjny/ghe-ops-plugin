# Enterprise Policies

> パス: `/enterprises/{enterprise}/settings/policies/repositories`

## 概要

Enterprise レベルのポリシー設定。リポジトリ操作、メンバー権限、Codespaces、Copilot、Actions、セキュリティなど多岐にわたるポリシーを Organization に対して強制する。[^1]

## サイドナビゲーション

| 項目 | パス | 備考 |
|------|------|------|
| Repository | `/enterprises/{enterprise}/settings/policies/repositories` | (Preview) 展開可能なサブメニュー |
| ↳ Repository | `/enterprises/{enterprise}/settings/policies/repositories` | リポジトリポリシー |
| ↳ Code | `/enterprises/{enterprise}/settings/policies/code` | コードポリシー |
| ↳ Code insights | `/enterprises/{enterprise}/settings/policies/code/insights` | |
| ↳ Code ruleset bypasses | `/enterprises/{enterprise}/settings/policies/code/bypass_requests` | |
| ↳ Custom properties | `/enterprises/{enterprise}/settings/custom-properties` | |
| Member privileges | `/enterprises/{enterprise}/settings/member_privileges` | |
| Codespaces | `/enterprises/{enterprise}/settings/codespaces` | |
| Copilot | `/enterprises/{enterprise}/settings/copilot` | |
| Actions | `/enterprises/{enterprise}/settings/actions` | |
| Hosted compute networking | `/enterprises/{enterprise}/settings/hosted_compute_networking` | |
| Projects | `/enterprises/{enterprise}/settings/projects` | |
| Advanced Security | `/enterprises/{enterprise}/settings/security_analysis_policies` | |
| Code Quality | `/enterprises/{enterprise}/settings/code_quality_policies` | (Preview) |
| Personal access tokens | `/enterprises/{enterprise}/settings/personal-access-tokens` | |

## セクション: Repository policies

> パス: `/enterprises/{enterprise}/settings/policies/repositories`

リポジトリに対する操作（削除、転送など）のポリシーを定義する。ルールセットベース。[^2]

### UI 要素

- アクションボタン: 「New policy」（新規ポリシー作成）
- ポリシー一覧テーブル（作成済みの場合）

## セクション: Code

> パス: `/enterprises/{enterprise}/settings/policies/code`

コードに関するポリシー（ブランチ保護、マージ要件等）。

## セクション: Member privileges

> パス: `/enterprises/{enterprise}/settings/member_privileges`

Enterprise メンバーのデフォルト権限を設定。

## セクション: Codespaces

> パス: `/enterprises/{enterprise}/settings/codespaces`

Codespaces の利用ポリシー。

## セクション: Copilot

> パス: `/enterprises/{enterprise}/settings/copilot`

Copilot のポリシー設定（AI Controls > Copilot とは別ページ）。

## セクション: Actions

> パス: `/enterprises/{enterprise}/settings/actions`

GitHub Actions の利用ポリシー（許可するアクション、デフォルト権限等）。[^3]

## セクション: Hosted compute networking

> パス: `/enterprises/{enterprise}/settings/hosted_compute_networking`

GitHub-hosted runners のネットワーク設定。

## セクション: Projects

> パス: `/enterprises/{enterprise}/settings/projects`

Projects の利用ポリシー。

## セクション: Advanced Security

> パス: `/enterprises/{enterprise}/settings/security_analysis_policies`

GitHub Advanced Security（GHAS）の有効化ポリシー。[^4]

## セクション: Code Quality (Preview)

> パス: `/enterprises/{enterprise}/settings/code_quality_policies`

コード品質に関するポリシー。

## セクション: Personal access tokens

> パス: `/enterprises/{enterprise}/settings/personal-access-tokens`

PAT（Personal Access Token）の利用ポリシー。fine-grained PAT の要求・承認フロー設定。[^5]

---

[^1]: [GitHub Docs: Enforcing policies for your enterprise](https://docs.github.com/enterprise-cloud@latest/admin/enforcing-policies)
[^2]: [GitHub Docs: About rulesets](https://docs.github.com/repositories/configuring-branches-and-merges-in-your-repository/managing-rulesets/about-rulesets)
[^3]: [GitHub Docs: Enforcing policies for GitHub Actions in your enterprise](https://docs.github.com/enterprise-cloud@latest/admin/enforcing-policies/enforcing-policies-for-your-enterprise/enforcing-policies-for-github-actions-in-your-enterprise)
[^4]: [GitHub Docs: About GitHub Advanced Security](https://docs.github.com/enterprise-cloud@latest/get-started/learning-about-github/about-github-advanced-security)
[^5]: [GitHub Docs: Setting a personal access token policy for your enterprise](https://docs.github.com/enterprise-cloud@latest/admin/enforcing-policies/enforcing-policies-for-your-enterprise/enforcing-policies-for-personal-access-tokens-in-your-enterprise)
