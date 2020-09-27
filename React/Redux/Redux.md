# Redux
- アプリケーションの状態を管理するためのツール
- Reactと相性がいい
- *最近は純粋なReduxよりもRedux Toolkitの方が使われるようになってきている

## Readuxの仕組み
- アプリケーションの状態たいを`store`で管理する
  - `Actions`を`Reducer`にディスパッチ（関数を渡す）する

- 1. reducerを宣言する
- 2. actionを宣言する
- 3. storeを宣言する

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

### Store
- アプリケーションの状態を保持するオブジェクト


## Reduxの3原則

### Single source of truth
- アプリケーションの状態を1つの`Store`で管理する
  - アプリの状態を管理しデバックが簡単になる

### State is read-only
- 状態は読み取り専用
- アクションには変化を加えるための値とその値をリデューサーでどのように処理するかを設定するためのタイプ（type）という値を引き渡す必要がある

### Changes are made with pure function
- 状態関数は純粋関数によって行わなければならない
- リデューサーは現在の状態とアクションを使用して、現在の状態に変更を加えることなく新しい状態を返す