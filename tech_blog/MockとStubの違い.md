Mockグループは、実行するだけで、返り値がない
Stubグループは、返り値がほしい

Mockグループ

- mock(フレームワークで作成)
  - jest.mock()
- spy(手書き)

Stubグループ

- stub(戻り値を返す用)
  - jestのreturnedValueのやつ
- dummy(引数を埋めるための固定値)
- fake(簡易実装)

Classical学派

- 共有依存をMock(他に影響を与える依存)
  - 多くはプロセスが依存(DB、APIなど)
    - managed dependency(アプリ専用のDB)
    - unmanaged dependency(外部API、SMTPサーバー)

依存の種類 例 テストでの扱い
プライベート依存（immutable） 値オブジェクト、定数 そのまま使う
プライベート依存（mutable） インメモリの協力者クラス そのまま使う
共有依存（managed） アプリ専用DB 統合テストで実物を使う
共有依存（unmanaged） SMTPサーバー、メッセージバス Mockで通信パターンを検証する

# References

[MockとStubの違いから学ぶテストダブルの正しい使い方](https://qiita.com/ryucciarati/items/db67a12d0c15588bdfc8)
