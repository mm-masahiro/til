# MVCモデル
- プログラムの役割を、`model`、`view`、`controller`の3つに分ける考え方

## Model
- DB関連の処理を担当
- DBに対して様々な問い合わせを行う

## View
- 画面表示（HTML）を担当

## Controller
- ユーザーからのリクエスト受付
- レスポンスを返す
- コントローラーは必ず`ApplicationController`を継承している
  - ↑で定義したルールはアプリケーションのすべてのアクションに反映される

## MVCモデルの処理の流れ
- 1. URLのリクエストから`router`を呼び出す
- 2. `router`により`controller`を呼び出す
- 3. ユーザーが行いたい動作を`controller`のアクションから呼び出す（メソッドを呼び出す）
- 4. `controkker`から画面に表示したいものを`model`に依頼する
- 5. `model`は依頼されたものをDBからとってきてそれを`controller`に返す
- 6. `controller`はDBから取ってきたものの情報を`view`に渡す
- 7. `view`は渡された情報を基にその情報を表示するHTMLを生成して`controlle`に返す
- 8. `controller`は受け取ったHTMLをユーザーにレスポンスとして返す