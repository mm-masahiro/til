# MySQL

## SELECT
- テーブルから指定するカラムのデータを選択する(参照するデータを取ってくるってイメージか？)
```
SELECT columnName FROM table_name
```
  - columnNameには式も入れられる
    - ex.
    ```
    SELECT name, gdp/population ~~~
    ```

## WHERE
- 既存のテーブル内のレコードを変更する際に条件を特定する
- ex.
  - 文字列での比較
  - 数値での比較
  - 論理演算(AND,OR,NOT)

## IN
- WHEREと一緒に使って複数の値を指定できる
```
SELECT ~~~
FROM ~~
WHERE ~~ IN (aa,bb,cc)
```

## LIKE
- `xxx`を含むものを特定できる
- `%`
  - 任意の0文字以上の文字列を一致させる

```
<!-- Yamadaが含まれるデータを取ってこれる -->
WHERE name LIKE ('Yamada%')
```

- `_`
  - 任意の1文字を一致させる

```
<!-- T○daのデータを取ってくる(TodaとかTadaとか) -->
WHERE name LIKE ('T_da')
```
