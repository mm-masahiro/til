# useMemo

## useMemoとは
- 値を保存するためのhook
  - 値は更新されない　←useStateの違い
  - キャッシュ

## 使い方
```
cont xxx = useMemo(func, [];
```
- `func`は関数で、何かしらの値を返す
- `func`が返した値が`xxx`に入る
  - ex.
  ```
  <!-- resultには42が入る -->
  const result = useMemo(() => 42, []);
  ```
- 2回目以降のレンダリングでは`func`を実行せずキャッシュから値をとってくる

- 第2引数は、「依存関係」を表している
  - ここに変数を入れると、入れた変数のいずれかの値が変わったときに`func`を再実行してくれる
    - ex. `props.id`が変わるたびに`expensiveFunc`が再実行
    ```
    const calcResult = useMemo(() => expensiveFunc(props.id), [props.id]);
    ```