# useEffect

## What's useEffect?
- 関数の実行のタイミングをReactのレンダリングの後まで遅らせるhook
  - API通信
  - DOMの書き換え

- クラスコンポーネントのライフサイクルメソッドに当たるもの
- `useEffect`は毎回のレンダーの後に呼ばれる
  
  - `useEffect()`の第2引数に[value]を渡すと、`value`に変化があった時のみ再レンダリングする

```
useEffect(func)

useEffect(() => {
    実行したい関数
})
```

- `useEffect`の中でクリーンアップ関数を登録できる
  - クリーンアップ関数を`return`することで、2度目以降のレンダリング時に前回の副作用を消すことができる
 - ＊Reactでの「副作用」というのは、「DOMの操作」であったり、『API通信」のことを指す