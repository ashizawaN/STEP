# Desing Document

## 宿題1
### 概要
モジュール化されたプログラムを変更して*や/に対応する
### 考え方
1. 入力をtokenに変換
2. *と/について評価し、+と-だけの新たな式を作る
3. 式をtokenに変換
4. +と-について評価

2の工程が新たに考えたい箇所なのでそれについて考える
- +と-の時は前から足し合わせを行っていたため、answer=0となっているがそこを変更する必要あり
- /の場合割る数が0の場合はエラーを返す必要がある
- 入力はtokens, 出力はtokens
- /と*がある前後の数について計算して、いらない要素を削除

## 宿題２
### 概要
書いたプログラムが正しく動いていることを確認するためのテストケースをrun_test()に追加する
### 考え方
テストケースで記述するべきことは下記のことである
- 最も小さいテストケース
  - 2*3や2/3など
- *と/が両方含まれるテストケース
  - 2*3/2など
- +-に*/を組み合わせたもの
  - */の優先度を高くする実装ができているかを確認するために 1+2/3 と 2/3+1 について考える

## 宿題３
### 概要
括弧に対応させ、テストケースを追加する
### 考え方
#### 括弧を対応させる
- LPARENとRPARENを追加
- homework_1_2のコードで、括弧内を評価し、括弧の外について評価する
  - LPARENがあったらRPARENが出現するまで括弧内の評価をする
  - 括弧がないtokenを作って今まで通りに計算する
  - 実装自体はできなくはないけど読みにくそうな感じ
- evaluate_multiply_divideとeval_parenthesesについて入力をtokensとindexにする
  - homework_1_2ではindexを1から始めているが、括弧内のみを計算しようとするとindexがないと再利用ができない
  - 入力されたindexから計算をするようにする
- 次の順で考える
1. 括弧を見つけて括弧内を計算 -> 括弧なしの式
2. homework_1_2と同様に計算


## 宿題４
### 概要
abs()、int()、round()に対応させ、テストケースを追加する
### 考え方
#### abs()、int()、round()に対応させる
- abs()だったら()の中を計算して絶対値を返す
- 絶対値 -> ()内<0だったら-1をかける
int()
- int()だったら()中を計算して小数点以下を切り捨て
round()
- round()だったら()内を計算して小数点第一位が5以上だったら一の位に1を足す