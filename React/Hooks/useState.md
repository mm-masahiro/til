# useState

## What's useState?
- 関数コンポーネントに状態を持たせるもの
  ```
  <!-- value=値を保持する変数,setValue=変数の値を変える関数,initialValue=初期値 -->
  const [value, setValue] = useState(initialValue);
  ```

  ```
  const [count, setCount] = useState(0);
  ```
- `setValue`は、引数に入れた値を`value`という変数に格納する関数
  - setValue(~~)は、`~~`をvalueに格納する