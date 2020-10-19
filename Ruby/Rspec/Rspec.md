# Rspec


## describe
- テストのグループ化を宣言

## context
- グループ化できる

## before
- `before do ... end`で囲まれた部分はexample(ブロックの中)の実行前に毎回呼ばれる
- beforeブロックの中でテストを実行する前の共通処理やデータのセットアップ等を行うことが多い

## let
- 変数として扱える
```
{ ... }の中の値がfooとして参照できる

let(:foo) { ... }
```

## subject
- テストコードをDRYにできる
- `subject` = テストの主語