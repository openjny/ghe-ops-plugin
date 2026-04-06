# ghe-ops-plugin

GitHub Enterprise の管理・運用に関する知識とスキルを提供する Agent Plugin。

## Install

### VS Code

```json
"chat.pluginLocations": {
    "openjny/ghe-ops-plugin": true
}
```

Ref: [Agent plugins in VS Code (Preview)](https://code.visualstudio.com/docs/copilot/customization/agent-plugins)

### GitHub Copilot CLI

```bash
copilot plugin install openjny/ghe-ops-plugin
```

Ref: [Finding and installing plugins for GitHub Copilot CLI - GitHub Docs](https://docs.github.com/en/copilot/how-tos/copilot-cli/customize-copilot/plugins-finding-installing)

## Structure

```
.claude-plugin/
  plugin.json         # Plugin metadata
skills/
  clickops/           # ClickOps（ブラウザ操作）支援
  ghe-webui/          # GitHub Enterprise Web UI ナビゲーション
  github-waf/         # GitHub Well-Architected Framework
```

## Plugin

### Skills

| Skill Name | Description |
|------------|-------------|
| clickops | ブラウザ操作を支援するスキル。ユーザーの指示に基づいて、GitHub Enterprise の Web UI を操作するための手順を提供します。 |
| ghe-webui | GitHub Enterprise の Web UI をナビゲートするためのスキル。ユーザーが特定の機能や設定にアクセスするためのガイドを提供します。 |
| github-waf | GitHub Enterprise の運用に関するベストプラクティスを提供するスキル。セキュリティ、パフォーマンス、信頼性などの観点から、GitHub Enterprise の運用を最適化するためのアドバイスを提供します。 |

## License

This project is licensed under the [MIT License](LICENSE).

Copyright (c) 2026 Junya Yamaguchi
