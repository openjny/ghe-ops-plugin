# VS Code 統合ブラウザ（Playwright ベース）

VS Code に組み込まれた Playwright ベースのブラウザツール群。

## ツール一覧

| ツール | 用途 | 制約 |
|--------|------|------|
| `open_browser_page` | 新しいページを開く | 同ホストのページがあれば再利用を優先 |
| `navigate_page` | URL 遷移・戻る・進む・リロード | `pageId` が必要 |
| `read_page` | ページの DOM スナップショット取得 | スクリーンショットより情報量が多い |
| `screenshot_page` | ページのスクリーンショット取得 | 視覚的な記録用。操作判断には `read_page` を使う |
| `click_element` | 要素をクリック | **ナビゲーション・タブ切替のみ使用** |
| `type_in_page` | テキスト入力・キー操作 | **検索・フィルタ入力のみ使用** |
| `hover_element` | 要素へのホバー | ツールチップ表示等 |
| `run_playwright_code` | カスタム Playwright コード実行 | スクロール等、他ツールで不十分な場合のみ |

## 操作手順

### ページを開く

```
open_browser_page(url="https://...")
```

既に同じホストのページが存在する場合は `navigate_page` で遷移する:

```
navigate_page(pageId="...", type="url", url="https://...")
```

### DOM スナップショットの取得

```
read_page(pageId="...")
```

- 出力形式: DOM ツリーのテキスト表現。各要素に `ref` 属性が付与される
- 出力が大きい場合（10KB超）はファイルに書き出される。`read_file` で内容を確認する
- `ref` を使って要素をクリック・ホバーできる

### 要素のクリック

`ref` を指定する方法（推奨）:

```
click_element(pageId="...", ref="e42", element="Organizations link")
```

セレクタを指定する方法:

```
click_element(pageId="...", selector="a[href='/orgs/myorg/people']", element="People link")
```

### テキスト入力

```
type_in_page(pageId="...", ref="e123", element="search box", text="keyword")
```

キー操作:

```
type_in_page(pageId="...", key="Enter")
```

### スクロール

ページ末尾へスクロール:

```
run_playwright_code(pageId="...", code="await page.evaluate(() => window.scrollTo(0, document.body.scrollHeight))")
```

特定の量だけスクロール:

```
run_playwright_code(pageId="...", code="await page.evaluate(() => window.scrollBy(0, 500))")
```

### スクリーンショット

ページ全体:

```
screenshot_page(pageId="...")
```

特定要素:

```
screenshot_page(pageId="...", ref="e100", element="members table")
```

## TIPS

- `read_page` の `ref` 値はページ遷移やリロードでリセットされる。遷移後は再度 `read_page` で最新の `ref` を取得すること
- `click_element` の `element` パラメータは必須。人間が読める説明を指定する（ツール内部では使われないが、ログの可読性に影響する）
- `run_playwright_code` 内では `page` オブジェクトが利用可能。`document` や `window` に直接アクセスせず `page.evaluate()` 経由で操作する
