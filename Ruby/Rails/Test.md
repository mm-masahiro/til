# Railsのテスト
- RSpecでRailsで作ったクラスやメソッドをテストする

## RSpec
- RSpecではテストコードのことをスペックと呼ぶ
- スペックを実行するためにはファイルの配置ルールと命名規則に従う必要がある
```
spec/
    models/
        モデルファイル名_spec.rb
    controllers/
        コントローラーファイル名_spec.rb
    views/
        erbファイル名_spec.rb
```

- 実行するためには以下のコマンドを実行
```
<Terminal>
bundle exec rspec
```

### itメソッド
- テスト対象のメソッドがどのような振る舞いをするかを文章で書く

### expecメソッド
- テスト対象を検証するためのメソッド
```
expect(実行結果).to eq 期待する結果
```


## テストの準備
- テスト対象とするサンプルモデルの作成
```
<Terminal>
rails g model xxx  column1:type column2:type ...
```


## テストファースト
- 考え方
  - 以下を繰り返す
  - 1. 期待するプログラムの振る舞いをスペックに記述する
  - 2. プログラムを実装する