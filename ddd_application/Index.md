## 1-1
ユースケース層だと考える。

ドメイン層は、普遍的な要素を列挙して定義する箇所である。
そのため、ドメイン層にアプリケーションの実行環境に依存した認証機能による、アクセス制御ロジックは書くべきではないと思う。
しかし、1日に5投稿しかできないなどのビジネスルール関するアクセス制御ロジックは、ドメイン層に書くべきだと思う。

参考になりそうなURL
- https://github.com/little-hands/ddd-q-and-a/issues/696
- https://github.com/little-hands/ddd-q-and-a/issues/576


## 1-2
認証に関連するロジックの実装はプレゼンテーション層か、インフラ層、認証ユーザーのインターフェースはアプリケーション層。
サードパーティ製のシステムを導入しているなら、認証に関連するロジックの実装はインフラ層になる。

参考になりそうなURL
- https://github.com/little-hands/ddd-q-and-a/issues/173
- https://github.com/little-hands/ddd-q-and-a/issues/206

## 1-3
認証に関するユーザーエンティティと、本来のユーザーエンティティで別々に実装する。

参考になりそうなURL
- https://github.com/little-hands/ddd-q-and-a/issues/493

## 2-1
ドメインサービス層で複数の集約を更新することが現実的であると思う。
ユースケース層で複数の集約を更新するのは、ドメインが漏れていると感じる。
