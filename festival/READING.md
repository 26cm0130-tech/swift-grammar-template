# 読解ノート：自分のアプリのコード3箇所

> **氏名：** （三浦崇志）
> **AI利用レベル：** 1（質問のみ。説明は自分の言葉で書く）
> **最終更新：** 2026-10-19

生成AIに書いてもらったコードでも、自分で書いたコードでもかまいません。自分のアプリの中から3箇所を選んで、次の3つの問いに答えてください。分からないところは、生成AIに「この行は何をしていますか」「この行を消すとどうなりますか」と聞いてかまいません。ただし、書くのは自分の言葉です。

> 💡 担任の先生の指示で、項目が増えることがあります。

---

## 箇所1：（プレイヤーの移動処理について）

```swift
func turnRight() {
    turn(to: state.player.direction.turnedRight, tutorialAction: .turnRight)
}

func moveForward() {
    moveOneTile(
        in: state.player.direction,
        action: .moveForward,
        blockedMessage: "前方は壁です。左右に向きを変えて進路を探そう！"
    )
}

func turnAround() {
    turn(to: state.player.direction.reversed)
}
```

**何をしているか：**
state.player.direction
現在のプレイヤーの向きを取得

.turnedRight
現在の向きから右へ90度回転した向きを取得

turn(to: ..., tutorialAction: .turnRight)
求めた向きに変更するため、別の関数 turn(...) を呼び出し。
turnの方で実際にプレイヤーの向きを更新する処理

func moveForward()
現在向いている方向へ1マス進もうとする処理

func turnAround()
現在向いている方向の反対側へ180度回転させる処理

**なぜこう書くのか：**
同一マス内での情報に、プレイヤーの座標位置＋プレイヤーの向きを表現するため

**もしこう書かなかったら：**
画面上で「上」を押したら座標の上、「右」を押したら座標の右へ、プレイヤーの座標が直接移動する

---

## 箇所2：（iOS 16への対応）

```swift
TextField(
    "",
    text: $playerName,
    prompt: Text("プレイヤー名を入力")
        .foregroundColor(Color.white.opacity(0.55))
)
    .font(DungeonTypography.maruMonica(size: 17))
    .foregroundColor(.white)
```

**何をしているか：**
foregroundStyleを使用していた部分を、
.foregroundColorに書き換えた

**なぜこう書くのか：**
iPhone8に対応させるため

**もしこう書かなかったら：**
iOS16のもので起動しない

---

## 箇所3：（見出し）

```swift
// コードを貼る
```

**何をしているか：**

**なぜこう書くのか：**

**もしこう書かなかったら：**

---

## 自分ではまだ説明できない箇所（正直に）

（アプリの中で「動いているけれど何をしているか分からない」ところを書く。ここに書いたものは、後期の文法の授業で分かるようになります。）
