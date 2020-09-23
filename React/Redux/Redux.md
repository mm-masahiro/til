# Redux
- アプリケーションの状態を管理するためのツール
- Reactと相性がいい

## Readuxの仕組み
- アプリケーションの状態たいを`store`で管理する
  - `Actions`を`Reducer`にディスパッチ（関数を渡す）する

### Actions
- `Action`は、ここのイベントに対する情報のこと
  - データを更新
  - データを削除
  - データを追加

- Reduxでは状態変化は全て`Action`を介して行う


### Reducer
- `Action`を使って状態変化を生じさせるには`Reducer`が必要
- ReducerにActionをディスパッチさせる（ReducerにActionを送信する）
- Reducerは元の状態を変更することなく新しい状態を返す

## Store
- アプリケーションの状態を保持するオブジェクト
