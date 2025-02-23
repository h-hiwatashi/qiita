---
title: immutableとmutableをFlutterとTypeScriptでまとめてみた
tags:
  - ""
private: false
updated_at: ""
id: null
organization_url_name: null
slide: false
ignorePublish: false
---

# この記事について

Flutter でよく immutable が出てきますが、TS ではあまり意識したことがなかったためまとめてみました。

# immutable and mutable

immutable（不変）と mutable（可変）は、オブジェクトの状態が変更可能かどうかを示す概念です。

## immutable（不変）

### 定義: 一度作成されたオブジェクトの状態を変更できない。

### 利点:

- スレッドセーフ: 複数のスレッドから同時にアクセスされても安全。
- 予測可能: オブジェクトの状態が変わらないため、予測しやすい。
- バグが少ない: 状態が変わらないため、予期しない変更によるバグが少ない。

### 例:

- TypeScript: const で宣言された変数や、Readonly 型。
- Flutter: final で宣言された変数や、const コンストラクタを持つクラス。

## mutable（可変）

### 定義: 作成されたオブジェクトの状態を変更できる。

### 利点:

- 柔軟性: 状態を変更できるため、動的な操作が可能。
- パフォーマンス: 状態を変更することで、再生成のコストを避けられる場合がある。

### 例:

TypeScript: let で宣言された変数や、通常のオブジェクト。
Flutter: var で宣言された変数や、通常のクラス。

# Flutter において

Riverpod が定番ですが状態管理を行う上で予期せぬエラーを防ぐため immutable が推奨されています。

immutable を実装するにはいくつか方法があります。

1. 自分で実装する。
1. @immutable アノテーション付ける。
1. freezed パッケージを使う。

この中で定番が freezed です。
freezed のメリットはこちらの記事が詳しいです。
https://zenn.dev/masarufuruya/articles/913beda4edf06d

freezed
https://pub.dev/packages/freezed#mixins-and-interfaces-for-individual-classes-for-union-types

# TypeScript において
