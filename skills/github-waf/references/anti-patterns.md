# Anti-patterns

GitHub 環境の健全性を損なう一般的なアンチパターンとその回避方法。

Source: https://wellarchitected.github.com/library/scenarios/anti-patterns/

## Platform Anti-Patterns

### Fragmented Organization Structure
単一の Organization で十分な場合に、チーム・プロジェクトごとに別の GitHub Organization を作成する。

**問題:** 権限・統合・ポリシー管理のオーバーヘッド増大、コラボレーション・可視性の阻害、ナレッジ共有の制限

**回避策:**
- GitHub プレゼンスの構造を慎重に計画
- 単一 Organization 内でチーム・プロジェクトボードを活用
- 権限・ポリシーの一元管理

## Planning Anti-Patterns

### Vague Requirements
不完全・曖昧な仕様での作業。

**問題:** 誤った実装、時間の浪費、フラストレーション

**回避策:**
- 要件収集・検証に十分な時間を確保
- Issue テンプレートで一貫した情報収集
- 複雑な要件を明確なサブ Issue に分解
- Copilot で曖昧な要件を明確化・テスト可能な基準にフォーマル化
- カスタム指示でドメイン固有の用語・受入基準を Copilot に学習

### Ineffective Work Management
GitHub Issues と Projects の不整合・不一貫な使用。

**問題:** プロジェクト管理の混乱、進捗・依存関係の追跡困難

**回避策:**
- 一貫したラベルシステム・マイルストーン・プロジェクトの使用
- Issue 作成・割り当て・クローズの標準ワークフロー文書化
- Issue テンプレート、定義済みラベル、プロジェクト自動化の使用
- Issue をコード変更にリンク

## Development Anti-Patterns

### Poor Commit Practices
大きく焦点の定まらないコミット、曖昧なコミットメッセージ。

**回避策:**
- 単一の論理的変更に焦点を当てた小さなアトミックコミット
- 何が変更され、なぜかを説明する明確で記述的なコミットメッセージ
- 組織全体で一貫したコミットメッセージフォーマット

### Inconsistent Branching Strategy
main ブランチへの直接作業、チーム間で一貫しないブランチアプローチ。

**回避策:**
- Git Flow or GitHub Flow のような明確なブランチ戦略を採用・文書化
- フィーチャーブランチの一貫した使用
- ルールセットによるブランチ戦略の自動強制

### Accumulating Technical Debt
既存のコード品質問題を放置して新機能を優先。

**回避策:**
- 技術的負債への定期的な時間確保
- 機能開発の一部としてリファクタリング
- Copilot でコード改善・テスト作成を支援
- 技術的負債メトリクスの測定・追跡

### Overengineering
不要に複雑なソリューションの構築、明確な価値のない機能追加。

**回避策:**
- MVP の定義・優先順位付け
- 将来のニーズの予測ではなく、現在の問題解決に焦点
- コードレビューで不要な複雑さを特定・課題提起
- Copilot でシンプルな代替案を提案

## Collaboration Anti-Patterns

### Bypassing Code Reviews
十分なコードレビューなしの PR マージ、表面的なレビュー。

**回避策:**
- 意味のあるレビューを必須とするルールセットの強制
- Copilot でファーストパスレビューと即時フィードバック
- 品質と建設的フィードバックを重視する文化の育成

### Delayed Feedback Cycles
アクションなしに長期間オープンのままの PR。

**回避策:**
- PR ワークフローへの自動チェック統合
- レビューターンアラウンド時間の期待値設定と強制
- PR エイジの監視とエスカレーション手順

## CI Anti-Patterns

### Insufficient Test Automation
主に手動テストへの依存、不十分な自動テストカバレッジ。

**回避策:**
- すべてのレベルで自動テストスイートを構築
- コード品質ゲートにテストカバレッジメトリクスを含める
- Copilot でテスト作成・メンテナンスを支援

### Neglecting Application Security
シークレット管理、依存関係更新、アクセスコントロールの見落とし。

**回避策:**
- GitHub Secrets で機密情報管理
- Dependabot で依存関係の自動更新
- 2FA 必須、定期的なアクセス権限レビュー
- Security Configurations でガードレールの一貫した強制

## CD Anti-Patterns

### Large Releases
多数の変更を蓄積した高リスクの大規模バッチリリース。

**回避策:**
- 継続的デリバリーで小さな頻繁なリリース
- フィーチャーフラグでデプロイと機能有効化を分離
- カナリアリリース・段階的ロールアウト

### Manual Deployment Processes
人間の介入に依存するデプロイメント。

**回避策:**
- コミットから本番までのデプロイパイプライン全体を自動化
- 必要な箇所にのみ承認ゲートを設置
- 残る手動プロセスの徹底的な文書化

## Application Security Anti-Patterns

### Detecting PII with Secret Scanning Custom Patterns
Secret Scanning のカスタムパターンで PII（社会保障番号、生年月日等）を検出すること。

**問題:**
- Secret Scanning はクレデンシャル・トークン（取り消し・ローテーション可能）向け。PII は恒久的で変更不可
- アラートは削除不可 — PII が永続的にアラートレコードに埋め込まれる
- GDPR, CCPA, HIPAA, PCI DSS のコンプライアンスリスク

**回避策:**
- Secret Scanning はクレデンシャル・API キー・トークンに限定
- PII 検出には専用 DLP ツールを使用
- DLP ツールを pre-commit hook としてデプロイ
- 既存カスタムパターンの PII 検出ルールを監査・削除
- 組織ポリシーでツールごとのデータタイプ対応を明文化
