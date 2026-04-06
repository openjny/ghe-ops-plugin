# github-enterprise-ops-plugin

GitHub Enterprise の管理・運用に関する知識とスキルを提供する VS Code Agent Plugin。

## Install

### VS Code

```json
"chat.pluginLocations": {
    "openjny/github-enterprise-ops-plugin": true
}
```

### GitHub Copilot CLI

```bash
copilot plugin install openjny/github-enterprise-ops-plugin
```

## Structure

```
.claude-plugin/
  plugin.json         # Plugin metadata
skills/               # Skills (追加予定)
```

## License

This project is licensed under the [MIT License](LICENSE).

Copyright (c) 2026 Junya Yamaguchi
