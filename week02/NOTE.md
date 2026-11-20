# week02 Optional

> **氏名：** 三浦崇志
> 
> **最終更新：** 2026-11-20
> 
> **AI利用レベル：** 演習は 2（生成コード可・4点セット必須）
> 
> **リファレンス：** swift-grammar-code の `reference/02_optional.md`

---

## 1. 教材コードで読めたこと（3行）

print(type(of: taroScore))    // Int ではありません

print(type(of: suzukiScore))

type(of: 変数) は、その変数が何型なのかを調べる。

let scoreOf: [String: Int] = [
    "電子太郎": 82,
    "電子花子": 55,
    "山田一郎": 91,
    "佐藤みなみ": 60,
    "グエン・アン": 72,
]

let taroScore = scoreOf["電子太郎"]
let suzukiScore = scoreOf["鈴木"]

までの情報から、82・・・などというIntで登録されている部分なので、

値の有無に関わらず、 Optional<Int>と出力される。

print(String(describing: taroScore))
print(String(describing: suzukiScore))

String(describing: ...) は、値の状態をそのまま文字列に変換して表示するための記述で

Optional(82)、nil

と表示される。文字列なので、数字ではなく、計算はできない。

• type(of:) で見ているのは「型の種類」（どちらも Int という型 ＝ Optional<Int>）

• String(describing:) で見ているのは「型の中身」（82 が入った型 Optional(82) か、空の型 nil か）

## 2. 演習の記録（4点セット）

### 演習1：（演習の名前）

**使ったプロンプト：**

自分で書いた

**AIの出力から自分が変えた点：**

yamadaScore = scoreOf["山田一郎"] ?? 0

suzukiPoint = scoreOf["鈴木"] ?? 0

**自分の言葉での説明（何を受け取り、何をして、何を返す）：**

scoreOf　云々 ?? 0

左に値があればそれ、なければ右の値を出力する。

**壊す実験（何を変えたら、何が起きたか）：**

””を外すとStringじゃなくなるから探せなくなってコンパイルエラーになる


### 演習2：（演習の名前）

**使ったプロンプト：**

自分で書いた

**AIの出力から自分が変えた点：**
```swift
for name in wanted {
    if let score = scoreOf[name] {
        found.append(name)
        foundTotal += score
    }
}
```
**自分の言葉での説明（何を受け取り、何をして、何を返す）：**

配列wantedの中にある名前を1つずつチェック、scoreOf に載っている人だけをリストに追加し、点数を合計する。

電子太郎　グエン・アンのnameとscoreがfoundにappendされる。

**壊す実験（何を変えたら、何が起きたか）：**

found.append(”山田”）

にすると、山田　山田　１５４　と出力される。


## 3. AI質問ログ

使った生成AI：（例：ChatGPT 無料版、Xcode の ChatGPT、Claude 無料版）

### Q1

**質問：**

なし

### Q2

**質問：**

なし

### Q3

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
