# 📜 Governance Pillar

ポリシーとコンプライアンスに沿った GitHub の管理・監督に焦点を当てる。権限、アクセスコントロール、監査ログを含む。

Source: https://wellarchitected.github.com/library/governance/

## Design Principles

### 1. Design for Auditability

すべてのアクションと変更の透明性、追跡可能性、管理承認との整合を確保する。

#### Start
- 各ロールのアクセス権と責任を明確に定義
- バージョン管理で全変更を追跡
- モニタリングが必要な重要リソースを特定し、継続的なログを実装

#### Mature
- ピアレビューとコードコミット承認を必要とする変更管理プロセスを確立
- 堅牢なブランチ戦略を実装
- ログフィルタリングメカニズムで関連ログのみ取得

#### Advance
- 不変ストレージでの監査証跡の継続的アーカイブ
- コミットの暗号署名
- リアルタイム分析と可視化のための運用ダッシュボード
- 本番ブランチへの自動コード導入前の厳格なレビュー要件

### 2. Design for Accountability

責任と透明性の環境を構築する。

#### Start
- リポジトリ、チーム、組織設定のオーナーシップを明確化
- 変更の意思決定プロセスを文書化
- システムの各側面に明確なアカウンタビリティラインを実装

#### Mature
- コード、意思決定、プロセスの文書化標準を確立
- 変更に対する必須レビュー・承認プロセスを実装
- トラッキング・プロジェクト管理機能でタスク割り当て・進捗追跡

#### Advance
- リアルタイムの進捗・アカウンタビリティダッシュボード
- 包括的なコントリビューション標準の策定

### 3. Design for Adaptability

組織や規制環境の変化に適応するガバナンスプロセスを構築する。

#### Start
- 変化に適応できるガバナンスプロセスの構築
- スケーラブルで変更容易なアクセスコントロールポリシー
- 履歴コンテキストを失わないインクリメンタル更新のドキュメント管理

#### Mature
- ガバナンス標準準拠の自動検証ワークフロー
- 組織のガバナンスコンプライアンスチームとの統合

#### Advance
- コンプライアンスレポートへの合理化されたアクセス
- 新規規制の監視とギャップ分析システム

### 4. Design for Control

プロジェクトが戦略目標に沿い、適切な管理承認を受けることを確保する。

#### Start
- 堅牢なアクセスコントロールと権限を実装
- ユーザー活動、システム変更、データアクセスのログキャプチャ計画
- 定期的なセキュリティ評価とコンプライアンスチェック
- 変更管理プロセス（開始→レビュー→実装）

#### Mature
- 多層ユーザーロール階層の設計
- ユーザーロール、コードレビューステータス、自動チェックに基づくコンテキスト固有のアクセスコントロール

#### Advance
- 異常検知のための機械学習アルゴリズム

### 5. Keep it Simple
- 明確でシンプルなガバナンスポリシー・手続き
- すべての関連ステークホルダーの積極的参加
- 実践的なリスク評価・軽減戦略
- 法律・規制・業界標準に整合したプラクティス
- 変更管理の原則の組み込み

## Checklist

### Auditability
- [ ] ブランチルールの理解とルール設置の確認
- [ ] PR 強制とブランチルールによるコード品質維持
- [ ] 必須ステータスチェックの有効化
- [ ] コードレビュー要件の設定
- [ ] コンプライアンスチェック（コードと依存関係）
- [ ] GitHub 監査ログの使用と監視
- [ ] 監査ログの適切な期間の保持
- [ ] バージョン管理による全変更の追跡
- [ ] 重要リソースの継続的ログ
- [ ] カスタムプロパティによるリポジトリ管理

### Accountability
- [ ] ロールベースアクセスコントロール（RBAC）の実装
- [ ] アクセス権のドキュメンテーション
- [ ] ユーザー活動の定期的モニタリング
- [ ] インシデントレスポンス手順の確立

### Adaptability
- [ ] ガバナンスポリシーの定期的レビュー・更新
- [ ] トレーニングプログラムの実施
- [ ] スケーラビリティの評価
- [ ] フィードバックメカニズムの確立

### Control
- [ ] 定期的なアクセスレビュー
- [ ] 構成管理プラクティスの実装
- [ ] バックアップ・リカバリプロセスの確保
- [ ] コンプライアンス監査の定期実施

### GitHub Enterprise 固有
- [ ] Enterprise 設定のレビュー・設定
- [ ] 高可用性・災害復旧計画（GHES）
- [ ] SSO/SCIM 等のセキュリティ統合
- [ ] パフォーマンスモニタリング
- [ ] データレジデンシー要件
- [ ] カスタムポリシーの策定
- [ ] ユーザープロビジョニングの自動化

## Key Recommendations

### Managing GitHub Copilot Premium Requests

**Premium Requests の基本:**
- Premium Requests = 高度な Copilot 機能の使用クレジット（Claude, Gemini 等の高度なモデル、Copilot cloud agent, Code Review）
- 毎月 1 日 00:00:00 UTC にリセット、未使用分は繰り越しなし
- Premium Requests の有効化は **ENABLED/DISABLED のポリシートグル**で管理（旧 $0 バジェット方式は 2025年12月に廃止）
- 基本オーバーレージ率: $0.04 USD/リクエスト
- 利用可能なモデルリストは頻繁に更新されるため [公式プランページ](https://docs.github.com/en/copilot/get-started/plans) を参照

**バジェット構成シナリオ:**
- Scenario A: Enterprise 全体で Premium Requests を有効化（ポリシーを ENABLED に設定 + 組織別バジェット上限）
- Scenario B: 選択的ユーザー有効化（組織ごとのバジェット）
- Scenario C: コストセンター管理（部門別バジェット割り当て）

**推奨バジェット例:**

| Team | Budget | License | Users |
|------|--------|---------|-------|
| Senior Developer | $500 | Enterprise | 15-20 |
| QA/Testing | $200 | Enterprise | 8-12 |
| DevOps | $300 | Enterprise | 5-8 |
| Junior Developer | $100 | Business | 20-30 |
| General Users | $0 | Business | 100+ |

**KPI:**

| KPI | Target | Alert Threshold |
|-----|--------|-----------------|
| Monthly Premium Request Growth | 10-20% MoM | >25% |
| Cost per Developer | $10-30/month | >$50/month |
| Budget Utilization | 70-85% | >90% |
| Feature Adoption | 60%+ DAU | <40% |
| Premium Model Usage | 20-30% | >50% |

**アラートレベル:**
- Early Warning: 75%
- Critical Alert: 90%
- Executive Notification: 95%
- Automatic Restrictions: 100%

### GitHub Enterprise Policies & Best Practices

**18 の重要ポリシー:**

1. **Actions 実行を特定リポジトリに制限**（Organization レベル）
2. **GitHub + Verified Creator のアクションのみ許可**（Enterprise レベル）
3. **ワークフロートークンのデフォルトを read-only に**（最小権限の原則）
4. **PR 自動承認を無効化**
5. **フォークの無効化**（不要な場合）
6. **リポジトリ可視性変更の制限**
7. **Fine-grained PAT の承認フロー実装**
8. **外部コラボレーター招待の制限**（Enterprise/Org Owner のみ）
9. **パブリックリポジトリ作成の禁止ポリシー**
10. **Webhook にシークレットを設定**
11. **Webhook に SSL を構成**
12. **Repository Rulesets の使用**（PR レビュー、必須チェック、保護ブランチ）
13. **CODEOWNERS の定義**
14. **コミット署名の強制**
15. **Rulesets のバイパスを許可しない**
16. **Runner グループを特定リポジトリに制限**
17. **Push Protection バイパスの制限**（特定ロール・チームのみ）
18. **監査ログストリーミングの設定**

### Managing Repositories at Scale

#### Custom Properties Best Practices

**コアプロパティスキーマ:**

| Property | Type | Purpose | Example Values |
|----------|------|---------|---------------|
| business-criticality | single-select | リスク評価とポリシーターゲティング | Critical, High, Medium, Low |
| owner-team | string | 責任とエスカレーション | "platform-team" |
| compliance-frameworks | multi-select | 規制要件の追跡 | SOX, HIPAA, GDPR, PCI |
| data-classification | single-select | データ取り扱い要件 | Public, Internal, Confidential, Restricted |
| environment | single-select | デプロイ層分類 | Production, Staging, Development |

**ターゲット:**
- プロパティカバレッジ: ≥90% のアクティブリポジトリ
- API スクリプトによる自動管理・検証
- ルールセット・ワークフロー自動化との統合

#### Rulesets Best Practices

- 組織レベルルールセットでポリシーを一元管理
- カスタムプロパティに基づくターゲティング
- バイパスアクティビティの監視
- 段階的な展開（Critical → High → Medium → Low）
