# model
- modelをgenerateすると、モデルがマイグレーションファイルが生成される
- モデル作成の流れ
  - 1. モデルとテーブルを作成する
    - `rails g model モデル名　カラム名:型`
  - 2. マイグレーションの実行
    - `rails db:migrate`
  - 3. カラムを追加する（必要に応じて）
    - `rails g migration add_カラム名_to_テーブル名　カラム名:型`

  ## マイグレーション
  - DBの構造を変更する手段を提供する
  - マイグレーション自体はDBに与える変更を定義した`change`メソッドの集まり
  ```
  <!-- マイグレーションの適用(マイグレーションの実行) -->
  rails db:migrate
  ```
  - `db:migrate`が実行されると、`db/development.sqlite3`というファイルが生成される　←DBの実態。DB Browser for SQLiteを使うとDBの構造を見れる。このコマンドでDBにテーブルを追加する
    - `rails g migration 

- データベースにオブジェクトを保存するには、`objectName.save`コマンドを実行する

## Active Record
- 有効性
- `User.find(idNum)`コマンドでオブジェクトを検索できる
- `User.find_by(オブジェクトのハッシュ)`コマンドで指定したハッシュを持つオブジェクトを検索できる
- オブジェクトの更新
  ```
  case1
  objectName.hashName = newHashData
  ex.
  user.name = "masahiro"

  最後に↓コマンドの実行でオブジェクトのデータの更新ができる
  user.save
  ```

  ```
  case2
  ↓のコマンドであれば変更と保存を同時にできる
  objectName.update(hash1: newHashData, hash2: newHashData)
  ```
- validation
  - データの属性に制約を課す
  - よく使われるvalidation
    - presence (存在性)
    - length (長さ)
    - format (フォーマット)
    - uniqueness (一意性)
    - confirmation (確認)

## .create
- モデルの生成から保存をひとまとめに実行するメソッド
- 保存したいカラムを引数として渡す
- ex
```
user.create(name: "Taro")
user.create(name: name)
```