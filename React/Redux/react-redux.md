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

- 3. `mapStateToProps`を追加してStoreの情報をpropsに反映させる
  - `mapStateToProps`
    - storeの情報をpropsに反映させることができる
    - 引数には自動的にstoreの中身が与えられ、その中身をどんな名前で個別のコンポーネントのpropsに渡すかを宣言する
      - 引数としてstateが与えられる
        - `state.xxx`としてreducerで宣言されたものが格納される

