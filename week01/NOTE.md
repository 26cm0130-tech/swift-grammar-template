# week01 型と制御構文の再確認、配列・辞書・範囲

> **氏名：** 三浦崇志
> **最終更新：** 2026-11-09
> **AI利用レベル：** 演習は 2（生成コード可・4点セット必須）
> **リファレンス：** swift-grammar-code の https://raw.githubusercontent.com/NakasenJEC/swift-grammar-code/refs/heads/main/week01/main.swift

---

## 1. 教材コードで読めたこと（3行）
let を使用した　className は "1CM1"　のまま変更されない
var を使用した　updateCount は　updateCount += 1　により変更される（初期値はなぜか１なので、現状必ず2回目の更新からはじまる）
switch case default で、点数によって表示されるテキストが変わる

## 2. 演習の記録（4点セット）

### 演習1：（演習の名前）

var passers: [String] = []
for i in 0..<names.count {
    if scores[i] >= scores[i] >= 60
        passers.append(names[i])
    }
}

**使ったプロンプト：**
自分で書いた

**AIの出力から自分が変えた点：**
自分で書いた

**自分の言葉での説明（何を受け取り、何をして、何を返す）：**
var passers: [String] = []で名前の配列
for i in 0..<names.count {　で０から４まで
if scores[i] >= scores[i] >= 60　
passers.append(names[i])　で６０点以上のiの番号の名前をpassersにappendする

**壊す実験（何を変えたら、何が起きたか）：**
for i in 0..<names.count {を、
for i in 1..<names.count { にした。
0 番目のデータの電子太郎・82点が飛ばされてピックされるのが３名になる


### 演習2：（演習の名前）
var highScorers = 0
for score in scoreOf.values {
    if score >= 80 {
        highScorers += 1
    }
}

**使ったプロンプト：**
自分で書いた
**AIの出力から自分が変えた点：**
自分で書いた
**自分の言葉での説明（何を受け取り、何をして、何を返す）：**
var highScorers = 0　で初期値０
for score in scoreOf.values { で　scoreOf　の右側（点数）だけを見て
    if score >= 80 {
        highScorers += 1　で80以上のscoreがあったらhighScorersに＋１

**壊す実験（何を変えたら、何が起きたか）：**
var highScorers = 0
for score in scoreOf.keys {
    if score >= 80 {
        highScorers += 1
    だと、StringとIntでコンパイルエラー

## 3. AI質問ログ
なし

### Q1

**質問：**
なし

### Q2
なし

### Q3
var total = 0
var average = 0.0
for score in scores {
    total += score
}
average = Double(total) / Double(scores.count)
**質問：**
なし

## 4. 今週の質問を振り返って
なし

## 5. 確認テストの振り返り（月曜の後に書く）

（間違えた問題と、なぜ間違えたか。次の週に同じ形式で出たら答えられるか）

---

> 💡 説明が書けないときは、コードを声に出して説明してみる。話せたら、それがそのまま文章になります。
> 💡 「なぜ」が浮かばないときは、その行を消す・数字を変えると何が起きるか試す。挙動の違いが「なぜ」のヒントになります。
> 💡 生成AIの説明が難しいときは、聞き返しフレーズ集（AI利用ルール）を使って、たとえ話で・どの行かを示しながら、もう一度聞き直す。
