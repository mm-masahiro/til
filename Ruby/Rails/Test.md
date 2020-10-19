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

## Rspecのキーワード
- describe
  - テストの対象になるものを書く（見出し的な）

- context
  - 「xxxの場合」というように前提条件を書く

- before
  - テスト全体のデータを投入する

- let
   - 変数のようなもの
   - itの中でデータを書き換えたりする

- subject
  - オブジェクト。itの中で対象となるテストデータを定義

- it
  - 「xxxとなること」みたいなテストの内容を書く

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

## Guard
- Guardを使うことでテストを自動的に実行できる
- Guardはファイルシステムの変更を監視し、ファイルなどを変更すると自動的にテストを実行してくれるツール

## assert_select
- 特定のリンクが存在するかどうかをチェックできる

```
<!-- "?"をabout_pathに置換している -->
assere_select "a[href=?]", help_path
```

## factory
### データを作成する
- `factory()`でファクトリ（テストデータの型）を定義する
```
`test/factories/users.rb`

factory :alice, class: User do
    name 'Alice'
    admin true
  end

  factory :bob, class: User do
    name 'Bob'
    admin false
  end

  # ...

end
```
### データを生成する
- ファクトリとして定義したデータはインスタンス化（生成）することでテストデータとして利用できる
```
alice = build(:alice)

Taroという属性値をファクトリの生成時に決定できる
alice = build(:alice, name:'Taro')
```

モデルのテストはDBとの連携がうまくいってるか、テーブルの制約がちゃんとかかってるかのチェック