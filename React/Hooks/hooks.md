# React-Hooks


## React-Hooksとは
- Reactの関数コンポーネントを高機能にしてくれるもの
  - Hooksにより関数コンポーネントからReactの機能に接続できるようになった
- Hooks以前は関数コンポーネントを使う意味はなかった
  - クラスコンポーネントの方が高機能だったため

## クラスコンポーネントの問題点
- 処理が散らばりやすい
  - 1つのコンポーネントの機能が1つの機能が、様々なメソッドの中に散らばっていく
    - 処理が複雑になる

  ```
  const App = () => {
    return <Counter />
  }

  class Counter extends Component {
    constructor(props)
    {
      super(props);
      this.state = {
        value : 0
      }
    }
    onIncrement = () => {
      this.setState({ value : this.state.value + 1});
    }
    render() {
      return (
        <div>
          <div>
            カウント値：{this.state.value}
          </div>
          <div>
            <button type="button" onClick={this.onIncrement}>+</button>
          </div>
        </div>
      );
    }
  }
  ```

## Hooksの特徴
- 関数コンポーネントに状態を持たせる
- 命名規則はすべて、`useXxxxx`という形