# store
- reducerからstoreを作成する
  - 1. reducerを呼び出す(importする)
  - 2. createsStoreを呼び出す(reduxから{createStore}wpiimportする)
  - 3. reducerを引数として、戻り値としてのstoreを取得する
  ```
  const sotre = createStore(reducers);
  ```
  - 4. storeを外部から呼び出せるようにする(exportする)

- Reactからstoreに変化を加えられるようにするために
  - 1. Actionを入れた関数を呼び出せるようにする
  - 2. `this.props.dispatch`を使ってactionをディスパッチする