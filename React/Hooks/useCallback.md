# useCallback

## useCallbackとは？
- useMemoの亜種
- 関数特化型のuseMemo
  - useMemoよりもコードを省略できる
  ```
  const xxx = useCallback(func, []);
  ```
- コールバック関数をキャッシュ化