# react-redux
- ReactとReduxは独立した別々のライブラリだが、その2つを結びつけるのが`react-redux`
  - reduxで作成したstoreからデータを取得するために使われる

## ReactからReduxのstoreのデータにアクセスする
- 1. `Provider`にstoreをセットする
  - React側からStoreの中のデータを利用できるようにする
  - コンポーネントにStoreを`store`として渡すことで子要素のコンポーネントからStoreの情報にアクセスできるようにする

- 2. connectを使用してコンポーネントからStoreにアクセスできるようにする
  - `connect`
    - 個別のコンポーネントからStoreの情報にアクセスできるようにする