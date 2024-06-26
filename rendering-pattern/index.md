## 課題1
### SSR (Server Side Rendering)
- サーバーサイドでHTMLを生成しクライアントに返す。
- データの取得はサーバーサイドで行う。
- レンダリングはサーバーサイドで行う。
- SEO対策がしやすい。

### CSR (Client Side Rendering)
- クライアントサイドでHTMLを生成することである。
- データの取得はクライアントサイドで行う。
- レンダリングはクライアントサイドで行う。
- SEO対策がしにくい。

### SSG (Static Site Generation)
- ビルド時にHTMLを生成することである。
- データの取得はビルド時に行う。
- レンダリングはビルド時に行う。
- SEO対策がしやすい。

## 課題2
## 課題3
- 週1回更新されるブログ : SSG
  - 更新頻度が低いため、ビルド時にHTMLを生成するSSGが適している。SEO対策もしやすい。
- ユーザーのコメントが随時追加されるクックパッドのようなサービス : SSR + CSR
  - ユーザーのコメントが随時追加されるため、クライアントサイドでデータの取得とレンダリングを行うCSRが適している。
- freeeのような会計サービス : SSR
  - 会計サービスのため、セキュリティやSEO対策が重要であるため、サーバーサイドでHTMLを生成するSSRが適している。
- 経営指標（OKRやKPIなど）を管理する社内サービス : CSR
  - 経営指標を管理するため、クライアントサイドでデータの取得とレンダリングを行うCSRが適している。SEO対策は不要。
- 社内SNS : CSR
  - 社内SNSのため、クライアントサイドでデータの取得とレンダリングを行うCSRが適している。SEO対策は不要。

## 参考記事
[SPA, SSR, SSGって結局なんなんだっけ？](https://zenn.dev/rinda_1994/articles/e6d8e3150b312d#ssg)
