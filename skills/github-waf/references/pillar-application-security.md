# 🔒 Application Security Pillar

アプリケーションのセキュリティ確保に焦点を当てる。Dependabot、Security Advisory、Code Scanning 等の活用を含む。

Source: https://wellarchitected.github.com/library/application-security/

> **製品変更（2025年4月〜）:** GitHub Advanced Security (GHAS) は **GitHub Secret Protection**（$19/月/committer）と **GitHub Code Security**（$30/月/committer）の2製品に分割された。本ドキュメント内の「GHAS」は、これら2製品の総称として使用する場合がある。

## Design Principles

### 1. Design for Security

セキュリティをアプリケーション開発と運用の各レベルに組み込む。

#### Start
- アプリケーションの各レベルにセキュリティ措置を組み込む
- 安全なコーディングガイドラインを確立
- 開発チームにセキュリティベストプラクティスを教育
- ロールベースのセキュリティトレーニングで継続的にスキル構築
- 強力なアクセスコントロール（最小権限）を実装

#### Mature
- SDLC 全体でソースコードのプロアクティブセキュリティを実施
- ソースコードのインシデントレスポンスプランを策定
- 機密性に基づくデータ分類
- ソフトウェアサプライチェーンの脆弱なコンポーネントからの継続的保護
- 包括的なインベントリを維持
- セキュリティ緩和策を定期的に検証

#### Advance
- 高度な予測分析と AI によるセキュリティ検出・修復
- セキュリティプラクティスのコード化（自動チェック + SDLC 統合）
- 隔離された一時的で安全な開発・ビルド・デプロイ環境
- セキュアなデフォルト設定
- 重要コンポーネントへのセキュリティコントロールの優先適用

### 2. Design for Compliance

規制・標準への準拠をアプリケーション設計に組み込む。

#### Start
- 適用される規制・標準の文書化
- SDLC 早期にコンプライアンスチェックを統合
- 定期的なコンプライアンス評価プロセスの確立

#### Mature
- 自動コンプライアンス監視ツールの導入
- コンプライアンス問題への対応プロセスの開発
- 今後の規制・標準への情報収集

#### Advance
- 高度なデータガバナンスフレームワークの採用
- 規制機関・業界フォーラムとの連携

### 3. Design for Proactivity

セキュリティ脅威を事前に予測・軽減する「シフトレフト」アプローチ。

#### Start
- 明確なセキュアソフトウェア開発ポリシーの策定
- セキュアコーディングプラクティスの文化育成
- 脆弱性のエンタープライズレポーティングシステムへの統合
- リスクの事前特定・軽減措置

#### Mature
- 開発チーム向けセキュリティインシデントレスポンスプラン
- セキュリティチャンピオンプログラムの実装
- セキュアソフトウェアポリシーの定期的レビュー・更新・共有

#### Advance
- 高度な予測分析と AI の活用
- 外部・内部セキュリティリサーチの促進
- ゼロトラストセキュリティの統合

### 4. Design for Awareness

セキュリティ意識を組織文化と開発ライフサイクルに深く組み込む。

#### Start
- 現在のセキュリティ意識レベルを評価
- 新入社員オンボーディングにセキュリティ意識を統合
- セキュリティリソースの内部リポジトリを開発
- 多様なトレーニング形式の実装

#### Mature
- 最近のセキュリティインシデントの共有
- プロアクティブなセキュリティ行動の認識・報奨

#### Advance
- シニアリーダーシップのセキュリティ教育への参加
- 外部エンティティとのベストプラクティス協働
- セキュリティ意識プログラムの継続的評価・進化

### 5. Keep it Simple
- 明確で管理しやすいセキュリティ措置
- セキュアコーディングプラクティスの重視
- SDLC 早期のセキュリティプロセス組み込み
- 堅牢な監視システムの実装
- 定期的なセキュリティトレーニングと意識向上プログラム

## Checklist

### Security
- [ ] 依存関係の自動脆弱性スキャン
- [ ] コードスキャンツールの CI/CD パイプライン統合
- [ ] シークレット管理ツールの使用とシークレットの定期ローテーション
- [ ] セキュリティポリシーの確認と強制
- [ ] 安全なコーディングガイドラインの確立と強制
- [ ] 厳格なアクセスコントロールと RBAC
- [ ] アクセスログの定期監査

### Compliance
- [ ] 適用される規制・標準の一覧化（GDPR, HIPAA 等）
- [ ] 定期的なコンプライアンス監査
- [ ] 包括的な監査ログ（改ざん防止・安全な保管）
- [ ] データ保護プラクティスの検証
- [ ] インシデントレスポンスプランの策定・定期演習
- [ ] コンプライアンストレーニングの提供

### Proactivity
- [ ] 定期的な脅威モデリング演習
- [ ] 定期的なペネトレーションテスト
- [ ] セキュリティパッチ・更新の適時適用
- [ ] 脆弱性管理プログラムの実装
- [ ] 継続的なセキュリティモニタリング

### Awareness
- [ ] 全従業員への継続的なセキュリティトレーニング
- [ ] 定期的なフィッシングシミュレーション
- [ ] セキュリティチャンピオンプログラムの確立
- [ ] セキュリティインシデント報告の明確なチャネル

### GitHub Enterprise 固有
- [ ] SSO 統合の実装
- [ ] GHES バックアップ・リカバリプロセスの確立・テスト
- [ ] API セキュリティ（認証・認可・トークン管理）
- [ ] モニタリング・アラーティングの設定
- [ ] サードパーティ統合のセキュリティレビュー

## Key Recommendations

### Securing Developer Workspace

開発者ワークスペースはコードが書かれ、テストされ、パッケージされる重要なセキュリティ境界。

**戦略:**
- MFA 必須の強力な ID 認証
- ワークスペース分離（Dev Container, Codespaces, Dev Box）
- 最小権限（非 root コンテナ実行）
- コミット署名（パスワードまたは生体認証付き）
- サードパーティ依存関係の慎重なレビュー・管理
- AI 支援開発のセキュリティ（AI 生成コードのレビュー、人間による制御）

**Dev Container ベストプラクティス:**
- 信頼できるソースからの最小ベースイメージ
- 非 root ユーザーでの実行（`containerUser`）
- Linux capabilities の制限（`--cap-drop=ALL`）
- Docker デーモンソケットの非公開
- ネットワークアクセスの制限

**AI 支援開発のセキュリティ:**
- AI 生成コードの慎重なレビュー
- AI が推奨する依存関係の検証（hallucinated パッケージ名に注意）
- 命令ファイルのプロンプトインジェクション検査
- MCP サーバー・ツールの評価

### Defending Against Dependency Supply Chain Attacks

6 層防御モデル:

1. **パッケージライフサイクルスクリプトの無効化** — `.npmrc`: `ignore-scripts=true`
2. **Dev Container による分離** — ホストへのアクセスを制限
3. **ユーザー操作を必要とする署名付きコミット** — 自動攻撃をブロック
4. **リポジトリルールセットの強制** — PR + ステータスチェック必須
5. **信頼された発行と検証** — OIDC ベースの trusted publishing, provenance attestation
6. **継続的な監視と対応** — Dependabot, Dependency Review, CodeQL, Secret Scanning

### Prioritizing Security Alert Remediation

**3 ステップ:**

1. **GitHub アラートメタデータの理解**
   - Code Security（GitHub Code Security）: 重大度、CWE、Copilot Autofix サポート
   - Secret Protection（GitHub Secret Protection）: 有効性（Active = 高優先度）
   - Dependabot: 重大度、EPSS、直接/推移的依存関係、スコープ

> **アクセス権限:** Dependabot アラートは Write/Maintain/Admin ロールが Read+Write アクセス可能。Security Manager ロールは全リポジトリへの Read アクセスとセキュリティアラートの表示・セキュリティ機能設定の管理が可能。Enterprise Security Manager (ESM) ロール（2025年10月〜 パブリックプレビュー）により Enterprise 全体のアラート・設定管理も可能。

2. **組織コンテキストの補足**（カスタムプロパティとして追加）
   - インターネット公開: 公開 = 大幅に高い優先度
   - 規制コンプライアンス: GDPR, HIPAA, PCI DSS
   - ビジネス重要度: Mission-Critical, High, Medium, Low
   - アプリケーションユーザー数

3. **Security Campaigns による高優先度アラートのターゲティング**
   - Code Scanning の Security Campaigns は GA
   - Secret Scanning の Security Campaigns はパブリックプレビュー（2025年9月〜）
   - 専用ダッシュボード、自動通知、締切/SLO、一元的追跡

### Securing GitHub Actions Workflows

**Key Strategies:**
1. **OIDC 認証** — 短期トークン、`sub` + `job_workflow_ref` でグラニュラー信頼
2. **リポジトリルールの設定** — PR、ステータスチェック、署名付きコミット必須
3. **最小権限** — 組織デフォルトを read-only、ジョブレベルで権限定義
4. **Dependabot** — 脆弱依存関係の自動検出
5. **アクション SHA ピンニング** — `actions/checkout@692973e...  # v4.1.7`（Enterprise/Org ポリシーで SHA ピニングを強制可能。2025年8月〜）
6. **可変依存関係を持つアクションの回避**
7. **ワークフローインジェクション回避** — `run:` ブロックでのユーザー入力のサニタイズ
8. **`pull_request_target` の回避** — 昇格権限で実行される危険性
9. **`workflow_run` のセキュリティ** — すべてのアーティファクトを非信頼として扱う
10. **`head.sha` を使用** — ブランチ名ではなく SHA で参照
11. **パブリックリポジトリに self-hosted runner を使用しない**
12. **許可アクションの制限** — Enterprise + 選択した非 Enterprise アクションのみ。特定アクションの明示的ブロック、SHA ピニング強制も設定可能（2025年8月〜）

### Enforce GitHub Code Security / Secret Protection at Scale

> 旧称: Enforce GHAS at Scale。2025年4月の製品分割により名称変更。

**戦略:**
1. ブランチ戦略の確立（GitHub Flow or Git Flow）
2. カスタムプロパティでリポジトリ管理
3. Security Configurations の使用
4. Repository Rulesets による補足的強制
5. アクセス権限の適切な設定
6. 例外プロセスの作成と監視

**Secret Scanning 強制:**
- Security Configurations で有効化
- Push Protection の強制
- Delegated Bypass でバイパス能力を制限（Organization レベル + Enterprise レベルの両方で設定可能。Enterprise レベルは 2025年9月〜）

**Dependency Scanning 強制:**
- Security Configuration 内で Dependabot を有効化
- 一元的な再利用可能ワークフローで Dependency Review Action を使用
- Repository Ruleset で必須ワークフローとして含める

**Code Scanning 強制:**
- Option 1: Security Configurations（簡単、CodeQL Default Setup）
- Option 2: Required Workflows + Repository Rulesets（柔軟、サードパーティツールサポート）

### GitHub Repositories Threat Model

**脅威アクター（9 分類）:**
- TA-01〜TA-09（インターネットアクセス → インサイダーまで段階的）

**主要脅威（8 分類）:**
- T-01: 公開リポジトリでのシークレット検索
- T-02: 権限外のプライベートリポジトリアクセス
- T-03: Danger Zone 設定の変更
- T-04: 重要ブランチのコミット履歴の改ざん/削除
- T-05: 不正な変更の送信
- T-06: 自分の PR の承認・マージ
- T-07: リポジトリの侵害
- T-08: 設定ミスの GitHub Workflow/Action の悪用
