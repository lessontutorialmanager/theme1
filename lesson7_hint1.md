```block
player.onChat("run", function () {
    agent.teleport(world(-165, 63, 176), SOUTH)
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 3; index++) {
            for (let index = 0; index < 4; index++) {
                agent.setItem(BRICKS, 1, 1)
                agent.place(FORWARD)
                agent.move(LEFT, 1)
            }
            agent.move(UP, 1)
            agent.move(RIGHT, 4)
        }
        agent.move(DOWN, 3)
        agent.move(LEFT, 5)
        agent.move(FORWARD, 1)
        agent.turn(RIGHT_TURN)
    }
})
```

```template
player.onChat("run", function () {

})
```

# LESSON5 家のかべを作ろう

## 目標

まずはこれから作るものの形を確認しよう！<br>
・チャットで「run」と入力したら、エージェントがたて５ブロック、横５ブロック、高さ３ブロックの家のかべを作るようにプログラミングをする<br>
・エージェントは初めにワールド-165 63 176、南(zのプラス方向)にテレポートする<br>
・ブロックはレンガブロック<br>
`||players.次のページから作り方を確認しましょう||`<br>
<img style="width:100%" src="https://i.ibb.co/SvzCP5g/iswall.gif"><br>

## 1.エージェントをテレポートさせよう

`||agent.エージェント||`ボタンをクリックしてその中の`||agent.エージェントを…へ西(xのマイナス方向)向きにテレポートさせる||`と書いてあるブロックを`||player.チャットコマンド～||`の中にドラッグしてみましょう<br>
`||agent.西(xのマイナス方向)▼||`をクリックして`||agent.南(zのプラス方向)▼||`にしましょう<br>

## 2.座標をしてみましょう

`||positions.ポジション||`ボタンをクリックしてその中の`||positions.ワールド0 0 0||`を`||agent.~0~0~0||`の上までドラッグします<br>
`||positions.ワールド0 0 0||`を`||positions.ワールド-165 63 176||`に変えましょう<br>

## 3.ループを追加してみましょう

`||loops.ループ||`ボタンをクリックしてその中の`||loops.くりかえし４回||`と書いてあるブロックを`||player.チャットコマンド～||`の中にドラッグしてみましょう<br>
さらに`||loops.くりかえし４回||`と書いてあるブロックを`||loops.くりかえし４回||`の中にドラッグしてみましょう<br>
`||math.４回||`を`||math.３回||`に変えましょう<br>
そしてその中に`||loops.くりかえし４回||`と書いてあるブロックをドラッグしてみましょう<br>

```block
player.onChat("run", function () {
    agent.teleport(world(-165, 63, 176), SOUTH)
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 3; index++) {
            for (let index = 0; index < 4; index++) {

            }
        }
    }
})
```

## 4.アイテムをしてみましょう

`||agent.エージェント||`ボタンをクリックしてその中の`||agent.エージェントに…を１個、自分のスロット１番に設定させる||`と書いてあるブロックを`||loops.くりかえし４回||`の中にドラッグしてみましょう<br>
`||blocks.土ブロック||`を`||blocks.レンガブロック||`に変えましょう<br>

```block
player.onChat("run", function () {
    agent.teleport(world(-165, 63, 176), SOUTH)
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 3; index++) {
            for (let index = 0; index < 4; index++) {
                agent.setItem(BRICKS, 1, 1)
            }
        }
    }
})
```

## 5.エージェントにブロックをおいてもらいましょう

`||agent.エージェント||`ボタンをクリックしてその中の`||agent.エージェントに前へ置かせる||`と書いてあるブロックを`||agent.エージェントに…を１個、…に設定させる||`の下にドラッグしてみましょう<br>

## 6.エージェントを動かしましょう

`||agent.エージェント||`ボタンをクリックしてその中の`||agent.エージェントを前に１ブロック移動させる||`と書いてあるブロックを`||agent.エージェントに前へ置かせる||`の下にドラッグしてみましょう<br>
`||agent.エージェントを前に１ブロック移動させる||`の`||agent.前▼||`をクリックして`||agent.左▼||`にしましょう<br>

## 7.エージェントを次のブロックをおく場所に動かしましょう⓵

`||agent.エージェント||`ボタンをクリックしてその中の`||agent.エージェントを前に１ブロック移動させる||`と書いてあるブロックを`||loops.くりかえし４回||`の下にドラッグしてみましょう<br>
`||agent.エージェントを前に１ブロック移動させる||`の`||agent.前▼||`をクリックして`||agent.上▼||`にしましょう<br>

```block
player.onChat("run", function () {
    agent.teleport(world(-165, 63, 176), SOUTH)
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 3; index++) {
            for (let index = 0; index < 4; index++) {
                agent.setItem(BRICKS, 1, 1)
                agent.place(FORWARD)
                agent.move(LEFT, 1)
            }
            agent.move(UP, 1)
        }
    }
})
```

## 8.エージェントを次のブロックをおく場所に動かしましょう⓶

`||agent.エージェント||`ボタンをクリックしてその中の`||agent.エージェントを前に１ブロック移動させる||`と書いてあるブロックを`||agent.エージェントを上に１ブロック移動させる||`の下にドラッグしてみましょう<br>
`||agent.エージェントを前に１ブロック移動させる||`の`||agent.前▼||`をクリックして`||agent.右▼||`にして、`||loops.１ブロック||`を`||loops.４ブロック||`にしましょう<br>

## 9.エージェントを次のかべを作る場所に動かしましょう⓵

`||agent.エージェント||`ボタンをクリックしてその中の`||agent.エージェントを前に１ブロック移動させる||`と書いてあるブロックを`||loops.くりかえし３回||`の下にドラッグしてみましょう<br>
`||agent.エージェントを前に１ブロック移動させる||`の`||agent.前▼||`をクリックして`||agent.下▼||`にして、`||loops.１ブロック||`を`||loops.３ブロック||`にしましょう<br>

```block
player.onChat("run", function () {
    agent.teleport(world(-165, 63, 176), SOUTH)
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 3; index++) {
            for (let index = 0; index < 4; index++) {
                agent.setItem(BRICKS, 1, 1)
                agent.place(FORWARD)
                agent.move(LEFT, 1)
            }
            agent.move(UP, 1)
            agent.move(RIGHT, 4)
        }
        agent.move(DOWN, 3)
    }
})
```

## 10.エージェントを次のかべを作る場所に動かしましょう⓶

`||agent.エージェント||`ボタンをクリックしてその中の`||agent.エージェントを前に１ブロック移動させる||`と書いてあるブロックを`||agent.エージェントを下に３ブロック移動させる||`の下にドラッグしてみましょう<br>
`||agent.エージェントを前に１ブロック移動させる||`の`||agent.前▼||`をクリックして`||agent.左▼||`にして、`||loops.１ブロック||`を`||loops.５ブロック||`にしましょう<br>

```block
player.onChat("run", function () {
    agent.teleport(world(-165, 63, 176), SOUTH)
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 3; index++) {
            for (let index = 0; index < 4; index++) {
                agent.setItem(BRICKS, 1, 1)
                agent.place(FORWARD)
                agent.move(LEFT, 1)
            }
            agent.move(UP, 1)
            agent.move(RIGHT, 4)
        }
        agent.move(DOWN, 3)
        agent.move(LEFT, 5)
    }
})
```

## 11.エージェントを次のかべを作る場所に動かしましょう⓷

`||agent.エージェント||`ボタンをクリックしてその中の`||agent.エージェントを前に１ブロック移動させる||`と書いてあるブロックを`||agent.エージェントを左に５ブロック移動させる||`の下にドラッグしてみましょう<br>

```block
player.onChat("run", function () {
    agent.teleport(world(-165, 63, 176), SOUTH)
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 3; index++) {
            for (let index = 0; index < 4; index++) {
                agent.setItem(BRICKS, 1, 1)
                agent.place(FORWARD)
                agent.move(LEFT, 1)
            }
            agent.move(UP, 1)
            agent.move(RIGHT, 4)
        }
        agent.move(DOWN, 3)
        agent.move(LEFT, 5)
        agent.move(FORWARD, 1)
    }
})
```

## 12.エージェントを次のかべを作る場所に動かしましょう⓸

`||agent.エージェント||`ボタンをクリックしてその中の`||agent.エージェント向きを左に変える||`と書いてあるブロックを`||agent.エージェントを前に１ブロック移動させる||`の下にドラッグしてみましょう<br>
`||agent.エージェントの向きを左に変える||`の`||agent.左▼||`をクリックして`||agent.右▼||`にしましょう<br>

```block
player.onChat("run", function () {
    agent.teleport(world(-165, 63, 176), SOUTH)
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 3; index++) {
            for (let index = 0; index < 4; index++) {
                agent.setItem(BRICKS, 1, 1)
                agent.place(FORWARD)
                agent.move(LEFT, 1)
            }
            agent.move(UP, 1)
            agent.move(RIGHT, 4)
        }
        agent.move(DOWN, 3)
        agent.move(LEFT, 5)
        agent.move(FORWARD, 1)
        agent.turn(RIGHT_TURN)
    }
})
```

## 10.『実行』ボタンをクリックしましょう

画面右下にある緑の『▶』ボタンをクリックして作ったプログラムを実行し、チャットコマンドで`||player.run||`と入力してみましょう
