## 課題1

[リポジトリ](https://github.com/Hikaru-Giannis/my-app/commit/bdc7234d896cd90894a61135d16b32f4f264b4bd)

引き分けのテストにおいて、現時点の私の実装では意味がない気がします。。。
## 課題2

### 課題2-1
メリット
- エンドユーザー視点でテストをすることができる。
  - 単体テストや結合テストでは検出できないバグの発見に繋がる。

デメリット
- 実行速度が遅い。
- メンテナンスコストが高い。
  - 膨大なシナリオになると管理が難しそうな印象。
- 原因追跡が単体テストや統合テストに比べると困難である。
  - プロダクションコードに問題がなくても、タイミングや実行環境等に影響され失敗するケースが発生しそう。

### 課題2-2
- メンテナンスコスト: 単体テスト > 統合テスト > E2E
- 実行速度: 単体テスト > 統合テスト > E2E
- 信頼度: E2E > 統合テスト > 単体テスト

https://kentcdodds.com/blog/static-vs-unit-vs-integration-vs-e2e-tests

### 課題2-3
- class
  - スタイルに関連することが多いなどが理由で、将来的に変更される可能性が高く、テストが落ちやすくなる。
- id
  - classよりは良いが、JavaScriptのイベントハンドラーなど利用されがちなため、容易にIDの変更ができないのが問題となる。
- 要素の文言
  - 他と同様にテキストの変更によって、テストが落ちる。
- `data-*`属性が推奨されている。

https://docs.cypress.io/guides/references/best-practices#Selecting-Elements

### 課題3
[リポジトリ](https://github.com/Hikaru-Giannis/my-app/commit/bdc7234d896cd90894a61135d16b32f4f264b4bd)

### 課題4
サードパーティー製のサーバー(ソーシャル認証など)を必要とする場合、E2Eテストはどのような対応をする必要があると思いますか？

<details>
<summary>解答</summary>
なるべく管理できるサーバーのみを対象にし、サードパーティ製のツールの動作確認はしない。
ログインなど必須の場合は何度もリクエストせず、結果をキャッシュさせたりする必要がある。
https://docs.cypress.io/guides/references/best-practices#Visiting-external-sites
</details>