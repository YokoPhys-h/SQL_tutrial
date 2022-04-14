# SQLを学んだときのTips

## データベースの選択
`use <データベース名>;`: 使用するデータベースを指定.

## データベースからデータを取得する
`select <列1>, <列2>... from <テーブル名>;`: テーブル名の列1, 列2, ...を取り出す.

`select <列1> as <名前1>, <列2> as <名前2>... from <テーブル名>;`: <テーブル名>から列1を<名前1>で取得する. `as`は省略可能.

`select * form <テーブル名>;`: テーブル名のすべてのデータを取り出す.

## コメントアウト
`-- hoge;`: 一行文をコメントアウトしたい場合.

`/**/`: 複数行のコメントアウト.

## 抽出したデータに演算を行う.
`select <列1> *1.08 from <テーブル名>;`: <列1>に1.08をかけた値で出力する.

## 条件を指定したデータ取得
`select <列1> form <テーブル名> where <列への条件>;`: whereの条件を満たす列のみが出力される. (例: `where price >= 1000;`)

## 各種演算
`select * from <DB>`: DBから全件取得.

`select * from <DB> where <hoge=1>`: DBからhogeの値が1の行を取得.

`select * from <DB> where "<hoge=1>" `: DBからhoge=1の行を取得. " "を忘れずに!

`select * from <DB> where <hoge > 1000>`: DBからhogeの値が1000より大きい列を取得.

`select * from <DB> where <hoge!=100>`: DBからhogeの値が100でないものを取得.

`select * from <DB> where <hoge in (1,2,3)>`: DBからhogeの値が1か2か3の行を取得.

`select * from <DB> where <hoge not in (1,2,3)>`: DBからhogeの値が1か2か3以外の行を取得.

`select * from <DB> where <hoge is null>`: DBからhogeの値がnullである行を取得.

`select * from <DB> where <hoge is not null>`: DBからhogeの値がnullでない行を取得.

`select * from <DB> where <hoge >= 1000 and hoge <= 2000>`: DBからhogeの値が1000以上かつ2000以下である行を取得. (論理積)

`select * from <DB> where <hoge = 1000 or hoge = 2000>`: DBからhogeの値が1000または2000である行を取得. (論理和)

## パターンマッチングによる絞り込み
`select <列1> from <DB> where <列名> like "<ワイルドカード文字>"`: DBから列の値がワイルドカード文字を満たすもの取得.

### ワイルドカード文字
1. `"あ%"`: "あ"から始まる文字列
2. `"%あ%"`: "あ"が含まれる文字列
3. `"%あ"`: "あ"で終わる文字列
4. `__あ`: 何かしらの2文字から始まり, "あ"で終わる文字列

## 取得件数の制限
`select * from <DB> limit 0,10`: DBから0から10番目まで取得. (0を省略すると自動的に0スタートになる.)

## 関数
`sum()`: 和を求める.

`avg()`: 平均を求める.

`min()`: 最小値を求める.

`max()`: 最大値を求める.

`count()`: 要素数を数える.

`count(distinct, hoge)`: hogeのうち, 重複を許さずに数える.

`abs()`: 絶対値を求める.

`concat(<hoge1>,<hoge2>)`: hoge1とhoge2の文字列の連結を行う.

### 追加オプション
`select <hoge> from <DB> group by <hoge2>`: hoge2をグループ(同じ値)でまとめて, hogeを取得.
