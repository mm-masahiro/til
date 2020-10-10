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

## LEFT
- 先頭のx文字目のところで文字列を切る
- ex
```
left('Hello',2) -> He
left('Hello',4) -> Hell
```

## サブクエリ
- 1つのクエリの中に含まれているもう1つのクエリ
- SELECT文で取得した結果を他のSELECT文やUPDATE文の中で利用する
  - WHere句の中で使われることが多いがそれに限定されているわけではない

### サブクエリで、取得した1つの値と比較する
```
select column_name1 from table_name1
where column_name1 = (select column_name2 from table_name2 where ~~~)
```

### サブクエリで取得した複数の値と比較する
- サブクエリで複数の値を取得し、その中のいずれか一つでも条件式を満たすかどうかを調べる
```
select column_name1 from table_name1
where column_name1 = ANY (select column_name2 from table_name2 where ~~~)
```

### サブクエリで取得した複数の値と比較する
- サブクエリで複数の値を取得し、その中の全ての値に対して条件式を満たすかどうかを調べる使い方
```
SELECT col_name1 FROM table_name
  WHERE col_name1 = ALL (SELECT col_name2 FROM table_name2 WHERE ...)
```

## CONCAT
- 文字列を結合するための関数
- 単純な文字列の結合ではあまり使われない
- 使用例として多いのは、
  - カラムと文字列を結合したい場合
  - 複数のカラム同士を結合したい場合

## MAX
- 特定のカラムの最大値を取ってくる

## 相関サブクエリ
- サブクエリの一種
- 外側のクエリの値をサブクエリ内で使用する