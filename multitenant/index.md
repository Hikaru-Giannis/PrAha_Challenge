## 課題１
## 解答
ミスが起こった原因
- 企業の機密情報に関わるのに対して、開発体制がずさんだったこと。
- 1つのアプリケーションで複数のテナントの情報を共有DBの共有テーブルで管理していたこと。

### 解決策
- 1つのアプリケーションでテナントごとにテーブルを利用して管理する。
- 1つのアプリケーションでテナントごとにDBを利用して管理する。
- シングルテナントアーキテクチャを採用する。
  - テナントごとにインフラとDBを用意する。
- Row Level Securityを採用する。
- フレームワークの機能やライブラリを利用する。(SmartHRでは、apartmentを利用)
- レビュー体制を設ける
- テストツールを利用する

## 課題2
マルチテナントアーキテクチャ

### テナントごとにデータベースを分割する方法

メリット
- テナントごとリクエストに柔軟に対応しやすい。
- 最も堅牢である。

デメリット
- マイグレーションコストが大きい。
  - テーブルのスキーマ変更などをテナントDB毎に行わなければならない。
- 運用の手間がかかる。
- インフラリソース、インフラ費用の効率が悪い。
- テナント間のやりとりが複雑化する。

### データベースは共有、テナント毎にスキーマを分割する、

メリット
- スキーマ単位で権限設定が可能なため、テナントごとにアクセス制御が可能であることから堅牢性はある。

デメリット
- マイグレーションコストが大きい。
  - テーブルのスキーマ変更などをテナントDB毎に行わなければならない。
- 運用に手間がかかる。
- テナント間のやりとりが複雑化する。
- テナントとテーブルのリレーションが煩雑化する。（外部キーなど）

### すべてのテナントで同じスキーマを使う
メリット
- インフラリソース、インフラ費用の効率が良い。
- マイグレーションコストが低い。

デメリット
- 他テナントへ最もカジュアルにアクセスすることが可能。(課題1のような問題が起きる。)
- 実装が煩雑化。
  - アプリケーションで制御する場合
    - where句
  - DBで制御する場合
    - Row-Level Securityで制御
    - ストアドプロシージャを実装しての制御



