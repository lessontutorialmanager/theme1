```block
player.onChat("run", function () {
    blocks.fill(
    BRICKS,
    world(-165, 66, 177),
    world(-161, 66, 181),
    FillOperation.Replace
    )
    blocks.fill(
    BRICKS,
    world(-165, 67, 178),
    world(-161, 67, 180),
    FillOperation.Replace
    )
    blocks.fill(
    BRICKS,
    world(-165, 68, 179),
    world(-161, 68, 179),
    FillOperation.Replace
    )
    agent.teleport(world(-166, 67, 176), SOUTH)
    for (let index = 0; index < 3; index++) {
        agent.setItem(BLACKSTONE, 7, 1)
        for (let index = 0; index < 7; index++) {
            agent.place(DOWN)
            agent.move(LEFT, 1)
        }
        agent.move(RIGHT, 7)
        agent.move(FORWARD, 1)
        agent.move(UP, 1)
    }
    agent.teleport(world(-166, 67, 182), SOUTH)
    for (let index = 0; index < 4; index++) {
        agent.setItem(BLACKSTONE, 7, 1)
        for (let index = 0; index < 7; index++) {
            agent.place(DOWN)
            agent.move(LEFT, 1)
        }
        agent.move(RIGHT, 7)
        agent.move(BACK, 1)
        agent.move(UP, 1)
    }
})


```

```template
player.onChat("run", function () {

})
```

# LESSON7 屋根を作ってみよう

## 目標

まずはこれから作るものの形を確認しよう！<br>
・チャットで「run」と入力したら、三角形の屋根ができるようにプログラミングをする<br>
・屋根の前面と後面はレンガブロックで作る<br>
・屋根はブラックストーンで４段で作る<br>
・屋根の幅は7ブロック<br>
`||players.次のページから作り方を確認しましょう||`<br>
<img style="width:100%" src="https://i.ibb.co/9cP9z6q/2024-04-01-161417.png"><br>

## 屋根の前面と後面を作ろう

三角屋根を作る前に屋根の土台となる部分を作らないと穴が開いてしまいます<br>
穴が開かないように土台を作るプログラムから作っていきましょう<br>
<img style="width:100%" src="https://i.ibb.co/6n232Ld/image.png"><br>
<img style="display: block; margin: 0 auto; width: 25%;" src="https://i.ibb.co/SKKzwsC/sita.png"><br>
<img style="width:100%" src="https://i.ibb.co/0FZYbqf/image.png"><br>

## 1.屋根の前面と後面を作ろう

`||blocks.ブロック||`ボタンをクリックしてその中の`||blocks.ブロックを並べる…範囲の始まり…範囲の終わり…モード…||`と書いてあるブロックを`||math.３つ||`取り出して`||player.チャットコマンド～||`の中にドラックしてみましょう<br>
`||blocks.草ブロック||`をクリックして`||blocks.レンガブロック||`にすべて変更しましょう<br>

```block
player.onChat("run", function () {
    blocks.fill(
    BRICKS,
    pos(0, 0, 0),
    pos(0, 0, 0),
    FillOperation.Replace
    )
    blocks.fill(
    BRICKS,
    pos(0, 0, 0),
    pos(0, 0, 0),
    FillOperation.Replace
    )
    blocks.fill(
    BRICKS,
    pos(0, 0, 0),
    pos(0, 0, 0),
    FillOperation.Replace
    )
})
```

## 2.座標を変えましょう

`||positions.ポジション||`ボタンをクリックしてその中の`||positions.ワールド0 0 0||`と書いてあるブロックを`||math.６つ||`取り出します<br>
`||math.３つ||`の`||blocks.ブロックを並べる…範囲の始まり…範囲の終わり…モード…||`の`||blocks.範囲の始まり…||`と`||blocks.範囲の終わり…||`それぞれに`||positions.ワールド0 0 0||`を入れます<br>

```block
player.onChat("run", function () {
    blocks.fill(
    BRICKS,
    world(0, 0, 0),
    world(0, 0, 0),
    FillOperation.Replace
    )
    blocks.fill(
    BRICKS,
    world(0, 0, 0),
    world(0, 0, 0),
    FillOperation.Replace
    )
    blocks.fill(
    BRICKS,
    world(0, 0, 0),
    world(0, 0, 0),
    FillOperation.Replace
    )
})
```

## 3.座標を変えましょう

`||positions.ワールド|`の座標を上から順に次のように変更しましょう<br>
・ワールド-165 66 177<br>
　ワールド-161 66 181<br>
・ワールド-165 67 178<br>
　ワールド-161 67 180<br>
・ワールド-165 68 179<br>
　ワールド-161 68 179<br>

```block
player.onChat("run", function () {
    blocks.fill(
    BRICKS,
    world(-165, 66, 177),
    world(-161, 66, 181),
    FillOperation.Replace
    )
    blocks.fill(
    BRICKS,
    world(-165, 67, 178),
    world(-161, 67, 180),
    FillOperation.Replace
    )
    blocks.fill(
    BRICKS,
    world(-165, 68, 179),
    world(-161, 68, 179),
    FillOperation.Replace
    )
})
```

## 屋根の右側を作ろう

次は家の右側の屋根の３段分を作りましょう<br>
プログラムを作る順番は次のようになります<br>
≪手順１≫エージェントをワールド-166 67 176、南向きにテレポートさせる<br>
≪手順２≫エージェントにブラックストーンを幅７ブロックで置かせる<br>
≪手順３≫エージェントを次のブロックを設置する場所に移動させる<br>
≪手順４≫手順２と手順３を３回くり返す<br>
<img style="width:100%" src="https://i.ibb.co/f8xBYvq/2024-04-01-221820.png"><br>

## 4.エージェントをテレポートさせよう

`||agent.エージェント||`ボタンをクリックしてその中の`||agent.エージェントを…へ西(xのマイナス方向)向きにテレポートさせる||`と書いてあるブロックを`||player.チャットコマンド～||`の中にドラックしてみましょう</br>
`||agent.西(xのマイナス方向)▼||`をクリックして`||agent.南(zのプラス方向)▼||`に変えましょう</br></br>

`||positions.ポジション||`ボタンをクリックしてその中の`||positions.ワールド0 0 0||`を`||agent.~0~0~0||`の上までドラッグします</br>
`||positions.ワールド0 0 0||`を`||positions.ワールド-166 67 176||`に変えましょう</br>

```block
player.onChat("run", function () {
    blocks.fill(
    BRICKS,
    world(-165, 66, 177),
    world(-161, 66, 181),
    FillOperation.Replace
    )
    blocks.fill(
    BRICKS,
    world(-165, 67, 178),
    world(-161, 67, 180),
    FillOperation.Replace
    )
    blocks.fill(
    BRICKS,
    world(-165, 68, 179),
    world(-161, 68, 179),
    FillOperation.Replace
    )
    agent.teleport(world(-166, 67, 176), SOUTH)
})

```

## 5.ループを追加してみましょう

`||loops.ループ||`ボタンをクリックしてその中の`||loops.くりかえし４回||`と書いてあるブロックを`||player.チャットコマンド～||`の中にドラックしてみましょう</br>
`||math.４回||`を`||math.３回||`に変えましょう</br></br>
さらにもう一つ`||loops.くりかえし４回||`と書いてあるブロックを`||loops.くりかえし３回||`の中にドラックして、`||math.４回||`を`||math.７回||`に変えましょう</br>

```block
player.onChat("run", function () {
    blocks.fill(
    BRICKS,
    world(-165, 66, 177),
    world(-161, 66, 181),
    FillOperation.Replace
    )
    blocks.fill(
    BRICKS,
    world(-165, 67, 178),
    world(-161, 67, 180),
    FillOperation.Replace
    )
    blocks.fill(
    BRICKS,
    world(-165, 68, 179),
    world(-161, 68, 179),
    FillOperation.Replace
    )
    agent.teleport(world(-166, 67, 176), SOUTH)
    for (let index = 0; index < 3; index++) {
        for (let index = 0; index < 7; index++) {

        }
    }
})

```

## 6.アイテムを変更してみましょう

`||agent.エージェント||`ボタンをクリックしてその中の`||agent.エージェントに…を１個、自分のスロット１番に設定させる||`と書いてあるブロックを`||loops.くりかえし７回||`の中にドラックしてみましょう</br>
`||blocks.草ブロック||`を`||blocks.ブラックストーン||`に変えましょう</br>
`||agent.エージェントに…を１個、自分のスロット１番に設定させる||`の`||blocks.１個||`を`||blocks.7個||`に変えましょう</br>

```block
player.onChat("run", function () {
    blocks.fill(
    BRICKS,
    world(-165, 66, 177),
    world(-161, 66, 181),
    FillOperation.Replace
    )
    blocks.fill(
    BRICKS,
    world(-165, 67, 178),
    world(-161, 67, 180),
    FillOperation.Replace
    )
    blocks.fill(
    BRICKS,
    world(-165, 68, 179),
    world(-161, 68, 179),
    FillOperation.Replace
    )
    agent.teleport(world(-166, 67, 176), SOUTH)
    for (let index = 0; index < 3; index++) {
        for (let index = 0; index < 7; index++) {
            agent.setItem(BLACKSTONE, 7, 1)
        }
    }
})


```

## 7.エージェントにブロックを置かせて移動させましょう

`||agent.エージェント||`ボタンをクリックしてその中の`||agent.エージェントに前へ置かせる||`と書いてあるブロックを`||agent.エージェントに…を１個、…に設定させる||`の下にドラックしてみましょう</br>
`||agent.前▼||`をクリックして`||agent.下▼||`に変更しましょう</br></br>
`||agent.エージェント||`ボタンをクリックしてその中の`||agent.エージェントを前に１ブロック移動させる||`と書いてあるブロックを`||agent.エージェントに下へ置かせる||`の下にドラックしてみましょう</br>
`||agent.エージェントを前に１ブロック移動させる||`の`||agent.前▼||`をクリックして`||agent.左▼||`に変更しましょう</br>

```block
player.onChat("run", function () {
    blocks.fill(
    BRICKS,
    world(-165, 66, 177),
    world(-161, 66, 181),
    FillOperation.Replace
    )
    blocks.fill(
    BRICKS,
    world(-165, 67, 178),
    world(-161, 67, 180),
    FillOperation.Replace
    )
    blocks.fill(
    BRICKS,
    world(-165, 68, 179),
    world(-161, 68, 179),
    FillOperation.Replace
    )
    agent.teleport(world(-166, 67, 176), SOUTH)
    for (let index = 0; index < 3; index++) {
        for (let index = 0; index < 7; index++) {
            agent.setItem(BLACKSTONE, 7, 1)
            agent.place(DOWN)
            agent.move(LEFT, 1)
        }
    }
})

```

## 8.エージェントを次にブロックを置く位置に移動させましょう

`||agent.エージェント||`ボタンをクリックしてその中の`||agent.エージェントを前に１ブロック移動させる||`と書いてあるブロックを`||loops.くりかえし７回||`の下にドラックしてみましょう</br>
`||agent.エージェントを前に１ブロック移動させる||`の`||agent.前▼||`をクリックして`||agent.右▼||`に変更して、`||math.１ブロック||`を`||math.７ブロック||`に変えましょう</br></br>
さらにもう一つ`||agent.エージェントを前に１ブロック移動させる||`と書いてあるブロックを`||agent.エージェントを右に７ブロック移動させる||`の下にドラックしてみましょう</br></br>
最後にもう一つ`||agent.エージェントを前に１ブロック移動させる||`と書いてあるブロックを`||agent.エージェントを前に１ブロック移動させる||`の下にドラックしてみましょう</br>
`||agent.エージェントを前に１ブロック移動させる||`の`||agent.前▼||`をクリックして`||agent.上▼||`に変えましょう</br></br>

```block
player.onChat("run", function () {
    blocks.fill(
    BRICKS,
    world(-165, 66, 177),
    world(-161, 66, 181),
    FillOperation.Replace
    )
    blocks.fill(
    BRICKS,
    world(-165, 67, 178),
    world(-161, 67, 180),
    FillOperation.Replace
    )
    blocks.fill(
    BRICKS,
    world(-165, 68, 179),
    world(-161, 68, 179),
    FillOperation.Replace
    )
    agent.teleport(world(-166, 67, 176), SOUTH)
    for (let index = 0; index < 3; index++) {
        for (let index = 0; index < 7; index++) {
            agent.setItem(BLACKSTONE, 7, 1)
            agent.place(DOWN)
            agent.move(LEFT, 1)
        }
        agent.move(RIGHT, 7)
        agent.move(FORWARD, 1)
        agent.move(UP, 1)
    }
})

```

## 屋根の左側を作ろう

次に家の左側の屋根の４段分を作りましょう<br>
≪手順１≫エージェントをワールド-166 67 176、南向きにテレポートさせる<br>
≪手順２≫エージェントにブラックストーンを幅７ブロックで置かせる<br>
≪手順３≫エージェントを次のブロックを設置する場所に移動させる<br>
≪手順４≫手順２と手順３を４回くり返す<br>
<img style="width:100%" src="https://i.ibb.co/PxLMnR2/2024-04-01-221901.png"><br>

## 9.エージェントをテレポートさせよう

`||agent.エージェント||`ボタンをクリックしてその中の`||agent.エージェントを…へ西(xのマイナス方向)向きにテレポートさせる||`と書いてあるブロックをプログラムの一番下にドラックしてみましょう</br>
`||agent.西(xのマイナス方向)▼||`をクリックして`||agent.南(zのプラス方向)▼||`に変えましょう</br></br>

`||positions.ポジション||`ボタンをクリックしてその中の`||positions.ワールド0 0 0||`を`||agent.~0~0~0||`の上までドラッグします</br>
`||positions.ワールド0 0 0||`を`||positions.ワールド-166 67 182||`に変えましょう</br>

```block
player.onChat("run", function () {
    blocks.fill(
    BRICKS,
    world(-165, 66, 177),
    world(-161, 66, 181),
    FillOperation.Replace
    )
    blocks.fill(
    BRICKS,
    world(-165, 67, 178),
    world(-161, 67, 180),
    FillOperation.Replace
    )
    blocks.fill(
    BRICKS,
    world(-165, 68, 179),
    world(-161, 68, 179),
    FillOperation.Replace
    )
    agent.teleport(world(-166, 67, 176), SOUTH)
    for (let index = 0; index < 3; index++) {
        for (let index = 0; index < 7; index++) {
            agent.setItem(BLACKSTONE, 7, 1)
            agent.place(DOWN)
            agent.move(LEFT, 1)
        }
        agent.move(RIGHT, 7)
        agent.move(FORWARD, 1)
        agent.move(UP, 1)
    }
    agent.teleport(world(-166, 67, 182), SOUTH)
})


```

## 10.ループを追加してみましょう

`||loops.ループ||`ボタンをクリックしてその中の`||loops.くりかえし４回||`と書いてあるブロックを`||player.チャットコマンド～||`の中にドラックしてみましょう</br></br>
さらにもう一つ`||loops.くりかえし４回||`と書いてあるブロックを`||loops.くりかえし４回||`の中にドラックして、`||math.４回||`を`||math.７回||`に変えましょう</br>

```block
player.onChat("run", function () {
    blocks.fill(
    BRICKS,
    world(-165, 66, 177),
    world(-161, 66, 181),
    FillOperation.Replace
    )
    blocks.fill(
    BRICKS,
    world(-165, 67, 178),
    world(-161, 67, 180),
    FillOperation.Replace
    )
    blocks.fill(
    BRICKS,
    world(-165, 68, 179),
    world(-161, 68, 179),
    FillOperation.Replace
    )
    agent.teleport(world(-166, 67, 176), SOUTH)
    for (let index = 0; index < 3; index++) {
        for (let index = 0; index < 7; index++) {
            agent.setItem(BLACKSTONE, 7, 1)
            agent.place(DOWN)
            agent.move(LEFT, 1)
        }
        agent.move(RIGHT, 7)
        agent.move(FORWARD, 1)
        agent.move(UP, 1)
    }
    agent.teleport(world(-166, 67, 182), SOUTH)
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 7; index++) {

        }
    }
})


```

## 11.アイテムを変更してみましょう

`||agent.エージェント||`ボタンをクリックしてその中の`||agent.エージェントに…を１個、自分のスロット１番に設定させる||`と書いてあるブロックを`||loops.くりかえし７回||`の中にドラックしてみましょう</br>
`||blocks.草ブロック||`を`||blocks.ブラックストーン||`に変えましょう</br>
`||agent.エージェントに…を１個、自分のスロット１番に設定させる||`の`||blocks.１個||`を`||blocks.7個||`に変えましょう</br>

```block
player.onChat("run", function () {
    blocks.fill(
    BRICKS,
    world(-165, 66, 177),
    world(-161, 66, 181),
    FillOperation.Replace
    )
    blocks.fill(
    BRICKS,
    world(-165, 67, 178),
    world(-161, 67, 180),
    FillOperation.Replace
    )
    blocks.fill(
    BRICKS,
    world(-165, 68, 179),
    world(-161, 68, 179),
    FillOperation.Replace
    )
    agent.teleport(world(-166, 67, 176), SOUTH)
    for (let index = 0; index < 3; index++) {
        for (let index = 0; index < 7; index++) {
            agent.setItem(BLACKSTONE, 7, 1)
            agent.place(DOWN)
            agent.move(LEFT, 1)
        }
        agent.move(RIGHT, 7)
        agent.move(FORWARD, 1)
        agent.move(UP, 1)
    }
    agent.teleport(world(-166, 67, 182), SOUTH)
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 7; index++) {
            agent.setItem(BLACKSTONE, 7, 1)
        }
    }
})

```

## 12.エージェントにブロックを置かせて移動させましょう

`||agent.エージェント||`ボタンをクリックしてその中の`||agent.エージェントに前へ置かせる||`と書いてあるブロックを`||agent.エージェントに…を１個、…に設定させる||`の下にドラックしてみましょう</br>
`||agent.前▼||`をクリックして`||agent.下▼||`に変更しましょう</br></br>
`||agent.エージェント||`ボタンをクリックしてその中の`||agent.エージェントを前に１ブロック移動させる||`と書いてあるブロックを`||agent.エージェントに下へ置かせる||`の下にドラックしてみましょう</br>
`||agent.エージェントを前に１ブロック移動させる||`の`||agent.前▼||`をクリックして`||agent.左▼||`に変更しましょう</br>

```block
player.onChat("run", function () {
    blocks.fill(
    BRICKS,
    world(-165, 66, 177),
    world(-161, 66, 181),
    FillOperation.Replace
    )
    blocks.fill(
    BRICKS,
    world(-165, 67, 178),
    world(-161, 67, 180),
    FillOperation.Replace
    )
    blocks.fill(
    BRICKS,
    world(-165, 68, 179),
    world(-161, 68, 179),
    FillOperation.Replace
    )
    agent.teleport(world(-166, 67, 176), SOUTH)
    for (let index = 0; index < 3; index++) {
        for (let index = 0; index < 7; index++) {
            agent.setItem(BLACKSTONE, 7, 1)
            agent.place(DOWN)
            agent.move(LEFT, 1)
        }
        agent.move(RIGHT, 7)
        agent.move(FORWARD, 1)
        agent.move(UP, 1)
    }
    agent.teleport(world(-166, 67, 182), SOUTH)
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 7; index++) {
            agent.setItem(BLACKSTONE, 7, 1)
            agent.place(DOWN)
            agent.move(LEFT, 1)
        }
    }
})


```

## 13.エージェントを次にブロックを置く位置に移動させましょう

`||agent.エージェント||`ボタンをクリックしてその中の`||agent.エージェントを前に１ブロック移動させる||`と書いてあるブロックを`||loops.くりかえし７回||`の下にドラックしてみましょう</br>
`||agent.エージェントを前に１ブロック移動させる||`の`||agent.前▼||`をクリックして`||agent.右▼||`に変更して、`||math.１ブロック||`を`||math.７ブロック||`に変えましょう</br></br>
さらにもう一つ`||agent.エージェントを前に１ブロック移動させる||`と書いてあるブロックを`||agent.エージェントを右に７ブロック移動させる||`の下にドラックして、`||agent.前▼||`をクリックして`||agent.後ろ▼||`に変えましょう</br></br>
最後にもう一つ`||agent.エージェントを前に１ブロック移動させる||`と書いてあるブロックを`||agent.エージェントを前に１ブロック移動させる||`の下にドラックして、`||agent.エージェントを前に１ブロック移動させる||`の`||agent.前▼||`をクリックして`||agent.上▼||`に変えましょう</br></br>

```block
player.onChat("run", function () {
    blocks.fill(
    BRICKS,
    world(-165, 66, 177),
    world(-161, 66, 181),
    FillOperation.Replace
    )
    blocks.fill(
    BRICKS,
    world(-165, 67, 178),
    world(-161, 67, 180),
    FillOperation.Replace
    )
    blocks.fill(
    BRICKS,
    world(-165, 68, 179),
    world(-161, 68, 179),
    FillOperation.Replace
    )
    agent.teleport(world(-166, 67, 176), SOUTH)
    for (let index = 0; index < 3; index++) {
        for (let index = 0; index < 7; index++) {
            agent.setItem(BLACKSTONE, 7, 1)
            agent.place(DOWN)
            agent.move(LEFT, 1)
        }
        agent.move(RIGHT, 7)
        agent.move(FORWARD, 1)
        agent.move(UP, 1)
    }
    agent.teleport(world(-166, 67, 182), SOUTH)
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 7; index++) {
            agent.setItem(BLACKSTONE, 7, 1)
            agent.place(DOWN)
            agent.move(LEFT, 1)
        }
        agent.move(RIGHT, 7)
        agent.move(BACK, 1)
        agent.move(UP, 1)
    }
})

```

## 14.『実行』ボタンをクリックしましょう

画面右下にある緑の『▶』ボタンをクリックして作ったプログラムを実行し、チャットコマンドで`||player.run||`と入力してみましょう
