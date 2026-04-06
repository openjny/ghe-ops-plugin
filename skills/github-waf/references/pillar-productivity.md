# ⚙️ Productivity Pillar

開発ワークフローの速度と効率を高める方法に焦点を当てる。自動化、CI/CD、GitHub Actions・Packages の活用を含む。

Source: https://wellarchitected.github.com/library/productivity/

## Design Principles

### 1. Design for Automation

自動化により、反復的で時間のかかるタスクを排除し、効率・精度・スケーラビリティを向上させる。

#### Start
- 現在の手動プロセスを把握し、優先順位を付ける
- 自動化の文化を醸成する
- 自動化コンセプトを文書化・一元管理する

#### Mature
- 自動化ワークフローとセキュリティ機能の学習セッションを提供
- 自動化のコスト対効果を評価
- プラットフォーム自動化導入の戦略を策定

#### Advance
- チーム横断の通知・更新・アクションを自動化
- コード実装・デプロイ・プロセス標準を自動検証で強制
- 継続的な監視と最適化

### 2. Design for Integration

システム、ツール、プロセスの統合によりサイロを排除し、リアルタイムのデータフローを実現する。

#### Start
- プラットフォーム統合の標準を確立
- 統合推進の責任者・チームを特定
- 統合プロセスのドキュメントを作成
- 主要な統合ポイントを特定・評価

#### Mature
- 優先度に基づいた統合の実装
- 統合プロセスの自動化強化

#### Advance
- 統合をチーム横断で推進（サイロ化防止）
- 統合ニーズと技術の継続的な評価

### 3. Design for Continuous Learning

継続的な学習により、変化への適応力、問題解決能力、モチベーションを向上させる。

#### Start
- 開発者トレーニングプログラムの戦略を策定
- 知識ギャップ（Pain Points）を特定

#### Mature
- 学習資材の一元リポジトリを構築
- 特定のツール・トレンドへの投資対効果を評価

#### Advance
- 業界トレンドと新ツールの学習セッションを開催
- Community of Practice を立ち上げる
- フィードバックとパフォーマンスデータでプログラムを改善

### 4. Design for Feedback

フィードバックにより、パフォーマンスの把握、目標の整合、継続的改善を推進する。

#### Start
- 建設的なフィードバック文化を促進
- 現在のフィードバック文化を評価
- 開発プロセスの早期にフィードバックメカニズムを統合
- 多様なフィードバックツール・手法を導入
- 定期的なレビュー・フィードバックセッションを確立

#### Mature
- 高度な分析ツールでフィードバックデータを分析
- 堅牢なフィードバックループを確立
- ステークホルダーからのフィードバック範囲を拡大

#### Advance
- AI を活用したフィードバック分析
- フィードバックを戦略的意思決定に統合
- 一元的なアプローチでフィードバックメカニズムをスケール

### 5. Design for Engineering System Success

エンジニアリングシステムの成功は、品質・速度・開発者の幸福度・ビジネス成果の4ゾーンにわたる継続的改善。

#### Start
- 現在の SDLC を監査し、ベースラインデータを収集
- 開発者インタビュー・アンケートで定性調査
- 4 つの成功ゾーンへのマッピング

#### Mature
- コスト・リスク・期待効果に基づく介入の評価・優先順位付け
- 4 ゾーンにわたる多様なフィードバックメカニズム
- パイロットで仮説を検証

#### Advance
- 成功した介入を組織全体にスケール
- AIOps と自動化でフィードバック・パフォーマンスデータを分析
- 成功と失敗から学ぶグロースマインドセットを醸成

### 6. Keep it Simple

- ワークフローを簡素化し、不要なステップ・複雑さを排除
- 反復的・時間のかかるタスクを自動化
- サードパーティ統合を活用
- ユーザーフィードバックとデータに基づき継続的に改善

## Checklist

### Automation
- [ ] すべての手動プロセスを文書化
- [ ] 反復的・時間のかかる・エラーの起きやすいタスクを特定
- [ ] 自動化ソリューションのスケーラビリティを評価
- [ ] CI/CD パイプラインを統合（GitHub Actions + GitHub-hosted runners）
- [ ] GitHub Enterprise 機能（Actions, Packages, Code Scanning, Secret Scanning, Dependabot）を活用
- [ ] 自動化ワークフローの継続的な監視と最適化

### Integration
- [ ] プラットフォーム統合の標準とガイドラインを定義
- [ ] 統合推進の責任者・チームを特定
- [ ] 統合プロセスのドキュメントを作成
- [ ] GitHub Enterprise API・Webhook でカスタム統合

### Continuous Learning
- [ ] 継続的改善と学習の文化を促進
- [ ] 新ツール・技術・ベストプラクティスのトレーニング提供
- [ ] GitHub Enterprise 機能のトレーニング提供
- [ ] フィードバックに基づく改善

### Feedback
- [ ] フィードバックチャネルの特定（アンケート、インタビュー、フォーム）
- [ ] GitHub Enterprise ユーザー向け専用フィードバックチャネル設置
- [ ] フィードバックデータの定期分析
- [ ] フィードバックループの閉鎖（確認・対応・報告）
- [ ] GitHub への定期的フィードバック（Services, Support, Partners 経由）

### Engineering System Success
- [ ] エンジニアリングプロセスの監査
- [ ] 4 つの成功ゾーンへの分類（Quality, Velocity, Developer Happiness, Business Outcomes）
- [ ] リーディング・ラギング指標のバランス
- [ ] 成功した介入のスケーリング

## Key Recommendations

### Engineering System Metrics

4 つの成功ゾーンと 12 の主要メトリクス:

| Quality | Velocity | Developer Happiness | Business Outcomes |
|---------|----------|-------------------|------------------|
| Change failure rate | Median lead time | Median flow state experience | % AI leverage |
| Median failed deployment recovery time | Deployment frequency | Median engineering tooling satisfaction | % Engineering expenses to revenue |
| Median code security & maintainability | Mean PRs merged per developer | Median Copilot satisfaction | % Feature engineering expenses |

重要な考慮事項:
- 定量・定性データの両方を使用
- コンパニオンメトリクスでコンテキストを提供（例: lead time + change failure rate）
- メトリクスは相互依存的 — 1 つのゾーンの改善が他を損なわないように
- ゲーミフィケーションとインセンティブの不整合に注意

### Adopting GitHub Copilot at Scale

#### ローンチ計画

**Pre-launch:**
- Copilot ポリシーの設定
- セルフサービスのオンボーディングプロセス
- ローンチ日のコミュニケーション
- KPI の定義（採用率、アクティビティ）
- Copilot Champions の特定

**Launch (Week 0):**
- 機会・メリット・利用可能性のコミュニケーション
- オンデマンドトレーニングとリソースの提供

**Post-launch (Weeks 1-4):**
- Expert Hub（内部コミュニティ）のデプロイ
- インストラクター主導セッション（ワークショップ、ハッカソン、ウェビナー）
- リマインダーメール・メッセージ

**Post-launch (Weeks 5-8):**
- 採用・アクティビティメトリクスの監視
- Copilot Usage API / User Management API によるレポーティング
- 高度なトレーニング
- フィードバック収集と改善

#### ライセンス割り当て戦略
- 組織全体 / 特定個人 / 特定チーム / Enterprise チーム
- 複数組織からのシート重複は自動的にデデュプリケーション
- セルフサービスプロセスの設定
- 非アクティブユーザーへのリマインダー自動化
- ライセンス自動取り消し時は通知猶予期間を設ける

#### 影響測定
- [Measuring Impact for GenAI Adoption](https://wellarchitected.github.com/library/scenarios/measuring-genai-impact) を参照
- 3 フェーズ: Onboard → Adoption → Success
