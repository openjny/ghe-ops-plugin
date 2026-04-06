# 📐 Architecture Pillar

GitHub デプロイの技術設計と構造に焦点を当てる。スケーラビリティ、信頼性、効率性を含む。

Source: https://wellarchitected.github.com/library/architecture/

## Design Principles

### 1. Design for Scalability

ユーザーとデータの成長に対応できるアーキテクチャを計画する。

#### Start
- 現在のシステムが支えるユーザー数・データ量・負荷を把握
- 使用中のリソース・サービスとスケール可能な追加メカニズムを理解
- 成長を見据えたアーキテクチャ計画
- スケーラブルなリソース・サービスの活用

#### Mature
- ガバナンス、スコープ管理、リスク管理の担当者・チームを特定
- 自動化を考慮したリソース・サービスの進化計画

#### Advance
- 需要に応じて動的にスケールするリソースの展開
- 非手動スケーラビリティのための自動化ワークフロー
- リソース・サービスのアップグレードと計画の更新

### 2. Design for Resiliency

障害や中断から耐え、回復できるシステムを構築する。

#### Start
- 障害データ収集システムの確認・確立
- 一定期間の障害発生状況の把握
- 障害排除措置の定義（シークレット管理、変更レビュー、セキュリティ機能）

#### Mature
- 障害防止措置を含むエンドツーエンドツールチェーンのリファレンスアーキテクチャ
- ビジネスユニットへの展開のフェーズ戦略

#### Advance
- 障害からの回復措置の実装
- 技術進化に応じた措置の更新と定期テスト

### 3. Design for Efficiency

リソース、ツール、プラクティスを最適化してボトルネックを排除する。

#### Start
- 現在のワークロードパフォーマンスのベースライン確立
- 開発プロセスの非効率性・ボトルネックの特定
- ボトルネック排除ツール・プラクティスの定義

#### Mature
- 新ツール・プラクティスを考慮したリファレンスアーキテクチャ
- 開発者への展開戦略

#### Advance
- 効率化ツール・プラクティスの実装
- 開発者トレーニング
- 新技術に基づくプロセス更新

### 4. Design for Disaster Recovery

主要インシデント・災害からの効果的な回復を確保する。

#### Start
- 現在の災害復旧メカニズムのベースライン把握
- 主要インシデント時の措置定義（自己修復機能を含む）
- 開発者への災害復旧計画トレーニング

#### Mature
- 監査スケジュールを含む災害復旧展開戦略
- 災害復旧メカニズムを組み込んだリファレンスアーキテクチャ

#### Advance
- 災害復旧メカニズムの実装
- ダウンタイム最小化、データ整合性確保、財務損失削減

### 5. Design for Modularity

疎結合・独立モジュールによる柔軟でスケーラブルなシステム設計。

#### Start
- 現在のシステムコンポーネントの特定
- コンポーネント分離の方法を設計

#### Mature
- コンポーネント分離のリファレンスアーキテクチャ
- シフト戦略のロードマップ
- パターン・ベストプラクティスの文書化

#### Advance
- 疎結合・独立モジュールへの構造化
- 開発者へのモジュラーマインドセットの浸透

### 6. Design for Interoperability

多様なシステム・サービス間のシームレスな相互作用を確保する。

#### Start
- 包括的で明確な API ドキュメント
- CI パイプラインの実装
- 小規模アジャイルチームの構築

#### Mature
- 統合のための明確なドキュメント・サポート
- Webhook によるリアルタイム更新

#### Advance
- 外部リソースの自動リンク・参照
- コラボレーションプラットフォームとの統合

### 7. Design for Observability

モニタリング、ログ、メトリクス収集、分散トレーシング、エラー追跡メカニズムを組み込む。

#### Start
- 現在のモニタリングレベルの理解
- モニタリング・ログ可能な対象のシステム監査
- 導入コスト対効果の評価

#### Mature
- 可観測性メカニズム導入のロードマップ
- 可観測性メカニズムの標準確立
- ユーザーフィードバック収集ツール

#### Advance
- 運用・状況ダッシュボードの実装・更新
- アラートメカニズムの確保
- 可観測性メカニズムのドキュメント更新

### 8. Keep it Simple
- 要件を満たす最もシンプルなアーキテクチャ
- 複雑なシステムを小さな独立モジュールに分解
- 反復タスク・ワークフローの自動化
- 包括的でユーザーフレンドリーなドキュメント
- 定期的なアーキテクチャ簡素化機会の評価

## Checklist

### Scalability
- [ ] リポジトリの命名規則と説明の確認
- [ ] カスタムプロパティによる動的管理
- [ ] モノリシック構造の不要な回避（or 必要性の判断）
- [ ] ブランチ保護ルールの使用
- [ ] コードモジュールの再利用性と疎結合
- [ ] 技術スタックの一貫性
- [ ] エフェメラルリソースのオンデマンド再作成
- [ ] 非エフェメラルリソースの成長余地確保

### Resiliency
- [ ] 障害時の継続運用機能
- [ ] バックアップ・リストアプロセスの確保・定期テスト
- [ ] 環境間の構成ドリフト最小化
- [ ] 高可用性構成
- [ ] フェイルオーバーメカニズムのテスト

### Efficiency
- [ ] 継続的なパフォーマンス監視と最適化
- [ ] リソース利用の効率化
- [ ] 反復タスクの自動化
- [ ] システムアーキテクチャの簡素化
- [ ] 明確で最新のドキュメント

### Disaster Recovery
- [ ] 災害復旧計画の策定・維持
- [ ] 災害復旧手順の定期テスト
- [ ] データレプリケーション戦略の実装
- [ ] force push 時の Git リポジトリ回復能力

### Modularity
- [ ] サービスのモジュール性と独立デプロイ
- [ ] コードベースのモジュール性
- [ ] マイクロサービスアーキテクチャの検討

### Interoperability
- [ ] API の適切なドキュメント・統合容易性
- [ ] 業界標準・ライセンス義務への準拠
- [ ] クロスプラットフォーム互換性

### Observability
- [ ] 包括的なログの実装
- [ ] モニタリングツールの使用
- [ ] アラートメカニズムの設定

### GitHub Enterprise Cloud 固有
- [ ] RBAC、定期監査、SSO
- [ ] セキュリティコンプライアンスの確認
- [ ] カスタム統合の評価・文書化
- [ ] データレジデンシー要件

### GitHub Enterprise Server 固有
- [ ] ネットワーク構成の最適化
- [ ] 定期的な更新・パッチ適用
- [ ] ハードウェアスケーラビリティ計画
- [ ] 堅牢なバックアップソリューション

## Key Recommendations

### Expanding Enterprise Custom Agents Context

30,000 文字制限を超えるカスタムエージェントのコンテキスト拡張に MCP を活用。

**アプローチ:**
1. `.github-private` リポジトリに `knowledge/` ディレクトリ構造を作成
2. トピック別のナレッジファイルを作成
3. エージェント markdown に GitHub MCP Server によるファイル取得命令を追加
4. PAT + `copilot` 環境でリポジトリごとに認証設定
5. 動作検証

**ベストプラクティス:**
- CODEOWNERS で明確なオーナーシップ
- 構造化されたフォーマット（見出し、リスト、コードブロック、テーブル）
- メタデータの含有（更新日、バージョン）
- PR レビュー必須
- ファイルは 10,000 文字以下に保つ

### Implementing Polyrepo on GitHub

ポリリポ運用モデル: Integration Layer (Meta-repo) パターン。

**Key Strategies:**
1. **Integration Layer (Meta-repo)** — コンポーネントバージョンの互換性検証
2. **Change Sets** — 親トラッキング Issue + 子 Issue での Cross-repo 調整
3. **ブランチと Merge 調整** — 一貫したブランチ命名規則・ルールセット
4. **Reusable Workflows** — セマンティックバージョニングの製品として扱う
5. **Component vs System Releases** — リリースケイデンスの分離
6. **Orchestration** — GitHub App によるクロスリポジトリ発見・実行

**Integration Manifest 例:**
```yaml
components:
  auth-service:
    repo: org/auth-service
    ref: v2.4.1
  billing-api:
    repo: org/billing-api
    ref: v1.12.0
```

**ブランチ調整オプション:**
- Option 1: Integration Branch（Release-train model — 最も信頼性が高い）
- Option 2: Meta-repo Manifest（Enterprise で一般的）
- Option 3: Versioned Artifacts（マージを完全に分離）
- Option 4: Linked PRs with Merge Gating（軽量だが自動化必須）

### Deploying Actions Runner Controller (ARC)

Kubernetes 上で GitHub Actions のセルフホストランナーを管理する ARC の展開。

### Accessing Private Networks from GitHub Actions Runners

プライベートネットワークへの GitHub Actions Runner からのアクセス方法。

### Scaling Git Repositories

**リポジトリアーキテクチャ戦略:**
- Monorepo vs Polyrepo の検討
- 大規模 Git リポジトリの管理
- Git LFS の使用判断基準
