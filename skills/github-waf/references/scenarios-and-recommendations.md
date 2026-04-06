# Scenarios & Cross-Cutting Recommendations

ピラー横断のシナリオベース推奨事項。

Source: https://wellarchitected.github.com/library/scenarios/

## Measuring Impact for GenAI Adoption

GitHub Copilot のような GenAI ツールの ROI を定量化するための構造化されたデータ駆動型測定フレームワーク。

### Phased Impact Model

#### Phase 1: Onboard Metrics
**Key Question:** ユーザーは企業管理の GenAI ツールに適切にプロビジョニングされているか？

**実装管理チェックリスト:**
- [ ] ライセンス付与管理プロセスの定義
- [ ] インフラセキュリティプロトコルの評価
- [ ] 情報保持・データ保護ポリシーのレビュー
- [ ] 信頼性・安全性メカニズムのレビュー
- [ ] OSS コンプライアンス要件の充足

#### Phase 2: Adoption Metrics
**Key Question:** ユーザーは期待通りに GenAI ツールを積極的に活用しているか？

**定性的測定:** フォーカスセッション、1on1、構造化アンケート、開発者エクスペリエンス調査
**定量的測定:**
- コード提案と受入率
- IDE 別の使用状況
- 異なる LLM モデルの利用
- チャット・コピー・受入等のインタラクティブイベント
- 時系列の利用トレンド

#### Phase 3: Success Metrics
**Key Question:** GenAI ツールはどのように測定可能なビジネス価値を創出しているか？

**共通インパクトシナリオ:**
1. **品質向上** — テストカバレッジ・信頼性、バグ・欠陥の削減、コード品質・保守性
2. **開発者生産性** — タスク完了時間、コードレビュー品質、オンボーディング時間
3. **セキュリティポスチャ** — 脆弱性検出・解決、セキュアコーディング導入、依存関係更新
4. **イノベーション加速** — 機能開発時間、プロトタイプ速度

## Monorepos

複数のプロジェクト・コンポーネントを単一リポジトリに統合するアプローチ。

**基本事項:**
- 統一コードベース: 複数チームが 1 つの（より少ない）リポジトリでコラボレーション
- コラボレーション: ツール、共有ライブラリ、統一コーディングガイドラインの考慮
- 複雑さのトレードオフ: 大規模コードベースは CI/CD パイプラインとGit操作の負荷増大

**主要考慮事項:**
- コードとチームの構造マッピング
- CI/CD ワークフロー（マトリクスビルド、ラベル付き PR、サブディレクトリベーストリガー）
- 正確な権限管理（高影響領域・ワークフローへのアクセス制限）
- ブランチ保護・レビューポリシー
- 依存関係とバージョン管理の堅牢なアプローチ
- クローン時間の管理

**参考:**
- [Scaling Git Repositories](https://wellarchitected.github.com/library/architecture/recommendations/scaling-git-repositories)
- [Monorepo Book](https://monorepo-book.github.io/)

## NIST SSDF Implementation with GitHub

NIST Secure Software Development Framework (SP 800-218) を GitHub Enterprise で実装するためのガイド。

### 設計戦略
1. **GitHub ネイティブセキュリティ機能の最大活用**
2. **多層防御の実装**
3. **CI/CD でのセキュリティチェック自動化**
4. **明確なガバナンス境界の確立**
5. **包括的な監査証跡の維持**

### 実装チェックリスト
- [ ] 組織レベルのセキュリティポリシー・設定の構成
- [ ] 全デフォルトブランチへのリポジトリルールセット実装
- [ ] マージ前のコードレビュー承認必須
- [ ] Secret Scanning と Push Protection の有効化
- [ ] Dependabot アラートとセキュリティ更新の有効化
- [ ] Code Scanning の設定
- [ ] CI/CD でのセキュリティスキャンの必須ステータスチェック化
- [ ] OIDC による CI/CD とクラウドプロバイダー間の認証
- [ ] RBAC の実装（チーム・カスタムロール）
- [ ] SAML SSO or OIDC の有効化
- [ ] 監査ログストリーミングの SIEM 連携
- [ ] 脆弱性トリアージ・修復プロセスの確立
- [ ] SBOM の生成・維持
- [ ] アーティファクトアテステーションの実装
- [ ] セキュリティ要件の GitHub Issues/Projects でのドキュメント化
- [ ] セキュリティポリシー・インシデントレスポンス手順の作成
- [ ] 開発者・管理者へのセキュリティトレーニング
- [ ] 重要アプリケーションの脅威モデリング・設計レビュー

### SSDF Practice Groups

#### PO: Prepare the Organization
- **PO.1:** GitHub Issues/Projects でセキュリティ要件を管理
- **PO.2:** GitHub RBAC、チーム、CODEOWNERS でロール・責任を定義
- **PO.3:** Security Configurations で組織全体のセキュリティ機能を有効化、Artifact Attestations
- **PO.4:** Repository Rulesets でソフトウェアセキュリティチェック基準を定義
- **PO.5:** GitHub Actions OIDC、環境保護ルール、GitHub-hosted runners

#### PS: Protect the Software
- **PS.1:** SAML SSO/OIDC、IP 許可リスト、チームベースアクセスコントロール、Repository Rulesets、CODEOWNERS、Push Rulesets、署名付きコミット
- **PS.2:** Artifact Attestations、Immutable Releases

#### PW: Produce Well-Secured Software
- Code Scanning (CodeQL)、Secret Scanning、Dependabot、Dependency Review

#### RV: Respond to Vulnerabilities
- セキュリティアラートの管理、修復、Security Campaigns

## Migration Scenarios

### Azure DevOps to GitHub Enterprise Migration

**フェーズ:** Plan → Assess → Setup → Test → Migrate → Post-Migration

### Checklist for Repository Migrations

リポジトリマイグレーションの計画・実行チェックリスト。

## Assessment Process

### Getting Started Checklist
1. GitHub or Partner のエキスパートとエンゲージ
2. 5 ピラーのフレームワークを理解
3. 初期 GitHub 環境レビュー
4. ステークホルダーインタビュー・アンケート
5. 分析・スコアリング
6. 推奨事項レビュー

### Assessment Deliverables
- エグゼクティブサマリー
- 詳細ドキュメント
- アクションアイテムを含むワークセッション

### Post-Assessment
1. 推奨事項の優先順位付け
2. アクションプランの策定
3. 継続的改善（反復的アセスメント）
