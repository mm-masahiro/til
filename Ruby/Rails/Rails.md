# Ruby on Rails
- `rails new アプリ名`で雛形を作成する
- アプリケーションを新規作成した後は`Bundller`を実行してアプリに必要なgemをインストールする
  - `アプリ名/Gemfile`に必要なものを書き加える
- `rails server (rails s)`でサーバーを起動
  - `Address already in use - bind(2) for "127.0.0.1" port 3000`というエラーが出たら・・・すでに同じポート番号のサーバーが使われている
    ```
    <Terminal>
    3000番ですでに繋がれてしまっているものを確認する
    lsof -i :3000

    kill -QUIT ~~~~
    ```

    ![](./Error_server.png)

## app/
- MVCを含む主要なアプリケーションコード

## app/assets
- CSSやJS、画像など

## MVC(Model-View-Controller)
- RailsはMVCというアーキテクチャパターンを採用している
- アプリケーション内のデータ（ユーザー情報など）とデータを表示するコードを分離する

### Railsの通信
- ブラウザがRailsアプリと通信する際にリクエストがコントローラに渡される
- コントローラーはビューを生成してHTMLなどをブラウザへ返す
- 動的なサイトでは、DBとの通信を担っているモデルとコントローラがやりとりを行い、モデルを呼び出した後、コントローラーはビューを描画する

## ルーター
- コントローラーとブラウザの間に配置される
- ブラウザからのリクエストをコントローラに振り分ける
- rootの設定方法
  - `app/config/root.rb`の編集
  ```
  Rails.application.routes.draw do
  <!-- root 'controller_name#action_name' -->
  root application#hello
  end
  ```