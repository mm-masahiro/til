# Ruby
- メソッドのアクセス権
  - public
  - protected
  - private
    - initializeメソッドとクラスの外に書いたメソッド
    - レシーバーを指定できない
    - privateなメソッドでも子クラス（サブクラス）でも呼び出せるし、オーバーライドもできる

    ```
    class Example

        private
            def sayHi
                puts "sayHi"
            end

        def sayHello
            puts "sayHello"
            <!-- クラスの中ではprivateなメソッドも使える -->
            puts sayHi
        end
    end

    tom = User.new

    <!-- privateなメソッドはレシーバーとして指定できない -->
    Example.new.private　←エラーに
    ```

- module
  - クラスのようにメソッドや変数をまとめられるが、インスタンスを作ったり継承したりはできない
  - 主な用途
    - 1.　名前空間として使う
      - 関連するメソッドや定数などをまとめてグループ化したい時にモジュール化させる

    - 2.　ミックスイン
      - 継承関係のない複数のクラス共通の機能を持たせる際に使われる

  - moduleの作り方
    - module名の1文字目は必ず大文字
    - クラスメソッドのように書けばOK
  ```
  //名前空間として使う
  module Movie
    def self.encode
        puts "encoding..."
    end
  end

  //ミックスインとして使う
  module Debug
    def info
        puts "#{self.class} debug info ..."
    end
  end

  class Player
    //includeでミックスインを呼び出す
    include Debug
  end

  class Monster
    include Debug
  end
  ```

- 例外処理
  - 何かの処理をしていて予期せぬ結果が発生した時に適切に処理していく方法
  ```
  x = gets.to_i
  
  //例外が発生しそうなところをbeginとendで囲む
  begin
    p 100 / x

  //例外が発生した場合の処理をrescureのあとに書いていく

  //発生した例外をexオブジェクトに入れる
  rescure => ex
    p ex.message
    puts "stopped" //自作のエラー文

  //例外が発生しようがしまいが最後に必ず実行したい処理はensureに続けて書く
  ensure
    puts " -- END -- "
  end
  ```

  ```
  //例外クラスの自作
  class MyErroe < StandardError; end  //StandardErrorはRubyの標準的な例外クラス

  begin
  ~~~~~
  raise MyError
  ~~~~~
  end
  ```

- カスタムヘルパー

## ブロック
- {}で囲まれるもの
- `|i|`のように、「|」で囲まれている変数をブロック変数と呼び、ブロックを操作する時に使う変数を指定する

## array.map(&:メソッド名)
- なにをしているか？
  - 配列の要素1つ1つに(&:メソッド名)で与えられたメソッドを呼んでいる

## ハッシュ
- 本質的にはハッシュと配列は同じであるが、ハッシュはインデックスとして整数値以外のものを使える
- ハッシュのインデックスをキーと呼ぶ
  - キーはオブジェクトである
- ハッシュはキーと値のペアを波カッコで囲んで表記する
- ハッシュでは要素の並び順が保証されない
  - 要素の順序が重要である場合は配列を使う
- ハッシュのキーとしてシンブルを使うのが一般的
  - シンボルの書き方→`:xxxx`
  - クォートで囲む代わりにコロンを前に置く
  ```
  user = {:name => "Xxxxx, :email => "aaaa@bbb"}
  ```
  ↓のようにしても書ける
  ```
  user = {name: "Xxxxx, email: "aaaa@bbb"}
  ```
- eachメソッドも取れる
  - ハッシュの場合eachメソッドのブロック変数は`key`と`value（値）`の2つになる