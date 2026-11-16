# LESSON2 かべを作ってみよう

```block
player.onChat("run", function () {
    agent.teleport(world(11, -21, 20), SOUTH)
    for (let index = 0; index < 5; index++) {
        for (let index = 0; index < 6; index++) {
            agent.setItem(PLANKS_BIRCH, 1, 1)
            agent.place(FORWARD)
            agent.move(LEFT, 1)
        }
        agent.move(UP, 1)
        agent.move(RIGHT, 6)
    }
})

```

```template
player.onChat("run", function () {
    agent.teleport(world(19, -21, -1), EAST)
    for (let index = 0; index < 5; index++) {
        agent.setItem(CARROTS, 1, 1)
        agent.till(FORWARD)
        agent.place(FORWARD)
        agent.move(LEFT, 1)
    }
})
```

## 目標（もくひょう）

先ほど作ったプログラムを改造（かいぞう）して、かべを作るようにしよう！<br>
・チャットで「run」と入力したら、エージェントができていない部分のかべを作るようにプログラミングをする<br>
・エージェントは、はじめにワールド11 -21 20、南(zのプラス方向)にテレポートする<br>
・ブロックをおく➡左に１ブロック動く を６回くり返して、次にブロックをおく場所にエージェントを動かす<br>
・かべは樺（かば）の板材（いたざい）でたて５ブロック、横６ブロックの大きさにする<br>
<img style="width:100%" src="https://i.ibb.co/mDdySpc/kabe.gif"><br>

## 畑を直したプログラムを使って、かべを作るプログラムを作ろう

まずは畑を直したプログラムを使って、かべを１列分作らせましょう<br>
<img style="width:100%" src="https://i.ibb.co/HrKGMGk/kabere.gif"><br>

## 1.いらないプログラムを消そう

`||agent.エージェントに前を耕（たがや）させる||`と書いてあるブロックにカーソルを合わせて右クリックをしましょう<br>
<img style="width:90%" src="https://i.ibb.co/ys9XXRF/l2deletemozi.png">をクリックするといらないブロックを消すことができます<br>
<img style="width:100%" src="https://i.ibb.co/s1twX0X/l4-2-1.gif"><br>
```block
player.onChat("run", function () {
    agent.teleport(world(19, -21, -1), EAST)
    for (let index = 0; index < 5; index++) {
        agent.setItem(CARROTS, 1, 1)
        agent.place(FORWARD)
        agent.move(LEFT, 1)
    }
})

````

## 2.座標を入力してみましょう

`||positions.ワールド19 -21 -1||`を`||positions.ワールド11 -21 20||`と入力しましょう<br>
そして`||agent.東(xのプラス方向)||`を`||agent.南(zのプラス方向)||`にしましょう<br>
```block
player.onChat("run", function () {
    agent.teleport(world(11, -21, 20), SOUTH)
    for (let index = 0; index < 5; index++) {
        agent.setItem(CARROTS, 1, 1)
        agent.place(FORWARD)
        agent.move(LEFT, 1)
    }
})
````

## 3.くりかえしの数を入力しましょう

今回はブロックを６個おくのでくりかえしの数も６回にしましょう<br>
`||functions.くりかえし５回||`を`||functions.くりかえし６回||`にしましょう<br>
```block
player.onChat("run", function () {
    agent.teleport(world(11, -21, 20), SOUTH)
    for (let index = 0; index < 6; index++) {
        agent.setItem(CARROTS, 1, 1)
        agent.place(FORWARD)
        agent.move(LEFT, 1)
    }
})
```

## 4.ブロックをえらびましょう

ブロックに樺（かば）の板材（いたざい）をえらびましょう<br>
`||blocks.ニンジン||`をクリックして`||blocks.樺（かば）の板材||`にしましょう<br>
```block
player.onChat("run", function () {
    agent.teleport(world(11, -21, 20), SOUTH)
    for (let index = 0; index < 6; index++) {
        agent.setItem(PLANKS_BIRCH, 1, 1)
        agent.place(FORWARD)
        agent.move(LEFT, 1)
    }
})
```

## エージェントを次にブロックをおき始める場所へ動かしましょう

１列分のブロックをおくプログラムができました！<br>
次にブロックをおきはじめる場所にエージェントを動かしてみましょう<br>
次のページにいく前に、下の赤いわくにエージェントを動かすには上に何ブロック、右に何ブロック動かせばいいか考えてみましょう<br>
<img style="width:100%" src="https://i.ibb.co/QbpVWxw/kabe3re.png"><br>
<img style="width:100%" src="https://i.ibb.co/9cBNtGL/kabe2re.gif"><br>

## 5.エージェントを上に動かしましょう

エージェントを上に１ブロック、右に６ブロック動かせばいいことがわかりましたか？さっそくそのプログラムを作りましょう<br>
`||agent.エージェント||`ボタンをクリックしてその中の`||agent.エージェントを前に１ブロック移動させる||`と書いてあるブロックを`||loops.くりかえし６回||`の下にドラックしてみましょう<br>
`||agent.エージェントを前に１ブロック移動させる||`の`||agent.前▼||`をクリックして`||agent.上▼||`に変更しましょう<br>
```block
player.onChat("run", function () {
    agent.teleport(world(11, -21, 20), SOUTH)
    for (let index = 0; index < 6; index++) {
        agent.setItem(PLANKS_BIRCH, 1, 1)
        agent.place(FORWARD)
        agent.move(LEFT, 1)
    }
    agent.move(UP, 1)
})
```

## 6.エージェントを右に動かしましょう

`||agent.エージェント||`ボタンをクリックしてその中の`||agent.エージェントを前に１ブロック移動させる||`と書いてあるブロックを`||agent.エージェントを上に１ブロック移動させる||`の下にドラックしてみましょう<br>
`||agent.エージェントを前に１ブロック移動させる||`の`||agent.前▼||`をクリックして`||agent.右▼||`に変更しましょう<br>
`||functions.１ブロック||`を`||functions.６ブロック||`にしましょう<br>
```block
player.onChat("run", function () {
    agent.teleport(world(11, -21, 20), SOUTH)
    for (let index = 0; index < 6; index++) {
        agent.setItem(PLANKS_BIRCH, 1, 1)
        agent.place(FORWARD)
        agent.move(LEFT, 1)
    }
    agent.move(UP, 1)
    agent.move(RIGHT, 6)
})
```

## プログラムを高さの数だけくりかえしましょう

これで１列分のブロックをおいて、次のブロックをおく場所に動くプログラムができました！<br>
さいごにこのプログラムをかべの高さの数だけくりかえすようにしましょう<br>
<img style="width:100%" src="https://i.ibb.co/PZ0hHKF/l4-q2loop.gif"><br>

## 7.くりかえしを入れてみましょう

`||loops.ループ||`ボタンをクリックしてその中の`||loops.くりかえし４回||`と書いてあるブロックで`||agent.エージェントを…テレポートさせる||`より下のプログラムをはさみましょう<br>
そして`||functions.４回||`を`||functions.５回||`にしましょう<br>
<img style="width:100%" src="https://i.ibb.co/tMvZHDM/l4-q2-7.gif"><br>
```block
player.onChat("run", function () {
    agent.teleport(world(11, -21, 20), SOUTH)
    for (let index = 0; index < 5; index++) {
        for (let index = 0; index < 6; index++) {
            agent.setItem(PLANKS_BIRCH, 1, 1)
            agent.place(FORWARD)
            agent.move(LEFT, 1)
        }
        agent.move(UP, 1)
        agent.move(RIGHT, 6)
    }
})

```

## 8.『実行』ボタンをクリックしましょう
画面右下にある緑の『▶』ボタンをクリックして作ったプログラムを実行し、チャットコマンドで`||player.run||`と入力してみましょう
```
