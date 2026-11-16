# LESSON1 畑を作ってみよう
```block
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

```template
player.onChat("run", function () {
	
})
```

## エージェントを動かすプログラムを作ろう @unplugged
エージェントを動かして畑や家のかべを作ろう！<br>
<img style="display: block; margin: auto;" height="50%" width="90%" src="https://i.ibb.co/fkYJjX0/hatake.gif">

## 目標（もくひょう）
まずはこれから作るものの形をかくにんしよう！<br>
・チャットで「run」と入力したら、エージェントが畑をたがやしてニンジンを植えるようにプログラミングをする<br>
・エージェントは、はじめにワールド19 -21 -1、東(xのプラス方向)にテレポートする<br>
・たがやす➡ニンジンを植える➡左に１ブロック動く を５回くり返す<br>
・畑は横５ブロックの大きさにする<br>
<img style="width:100%" src="https://i.ibb.co/zHC48DV/hatakere2.gif"><br>

## エージェントに１ブロック分の畑をたがやして、ニンジンを植えさせよう
まずはエージェントに１ブロック分の畑をたがやして、ニンジンを植えてもらいましょう<br>
エージェントの動きは次の１～４のようにします<br>
１.エージェントにニンジンをわたす<br>
２.前をたがやす<br>
３.ニンジンを植える<br>
４.エージェントを左に１ブロック動かす<br>
<img style="width:100%" src="https://i.ibb.co/HrGh8Gx/hatakere3.gif"><br>

## 1.エージェントにアイテムをわたしましょう

`||agent.エージェント||`ボタンをクリックしてその中の`||agent.エージェントに…を１個、自分のスロット１番に設定（せってい）させる||`と書いてあるブロックを`||player.チャットコマンド～||`の中にドラックしてみましょう<br>
`||blocks.土ブロック||`をクリックして`||blocks.ニンジン||`にしましょう<br>
<img style="width:100%" src="https://i.ibb.co/YWm8RLm/l4-1.gif"><br>
```block
player.onChat("run", function () {
    agent.setItem(CARROTS, 1, 1)
})
```

## 2.エージェントに畑をたがやさせましょう

`||agent.エージェント||`ボタンをクリックしてその中の`||agent.エージェントに前を耕（たがや）させる||`と書いてあるブロックを`||agent.エージェントに…設定させる||`の下にドラックしてみましょう<br>
<img style="width:100%" src="https://i.ibb.co/DfhRHvZ/l4-2.gif"><br>
```block
player.onChat("run", function () {
    agent.setItem(CARROTS, 1, 1)
    agent.till(FORWARD)
})
```

## 3.エージェントにニンジンを植えてもらいましょう

`||agent.エージェント||`ボタンをクリックしてその中の`||agent.エージェントに前へ置（お）かせる||`と書いてあるブロックを`||agent.エージェントに前を耕させる||`の下にドラックしてみましょう<br>
<img style="width:100%" src="https://i.ibb.co/KKxj9Cb/l4-3.gif"><br>
```block
player.onChat("run", function () {
    agent.setItem(CARROTS, 1, 1)
    agent.till(FORWARD)
    agent.place(FORWARD)
})

```

## 4.エージェントを動かしましょう

`||agent.エージェント||`ボタンをクリックしてその中の`||agent.エージェントを前に１ブロック移動（いどう）させる||`と書いてあるブロックを`||agent.エージェントに前へ置かせる||`の下にドラックしてみましょう<br>
`||agent.エージェントを前に１ブロック移動させる||`の`||agent.前▼||`をクリックして`||agent.左▼||`に変更しましょう<br>
<img style="width:100%" src="https://i.ibb.co/fnkvV5g/l4-4.gif"><br>
```block
player.onChat("run", function () {
    agent.setItem(CARROTS, 1, 1)
    agent.till(FORWARD)
    agent.place(FORWARD)
    agent.move(LEFT, 1)
})

```

## エージェントに同じ動きをくりかえさせましょう
これで１ブロック分の畑をたがやして、ニンジンを植えてもらうプログラムができました<br>
つぎはこの動きを５回くりかえさせましょう<br>
<img style="display: block; margin: 0 auto; width:50%" src="https://i.ibb.co/HrGh8Gx/hatakere3.gif"><br>
<img style="display: block; margin: 0 auto; width: 25%;" src="https://i.ibb.co/SKKzwsC/sita.png"><br>
<img style="width:100%" src="https://i.ibb.co/zHC48DV/hatakere2.gif"><br>


## 5.くりかえしを入れてみましょう

`||loops.ループ||`ボタンをクリックしてその中の`||loops.くりかえし４回||`と書いてあるブロックで今までに作ったプログラムをはさみましょう<br>
そして`||functions.４回||`を`||functions.５回||`にしましょう<br>
<img style="width:100%" src="https://i.ibb.co/w07tkcz/l4-5.gif"><br>
```block
player.onChat("run", function () {
    for (let index = 0; index < 5; index++) {
        agent.setItem(CARROTS, 1, 1)
        agent.till(FORWARD)
        agent.place(FORWARD)
        agent.move(LEFT, 1)
    }
})
```

## エージェントを畑をたがやしはじめる場所にテレポート
さいごにエージェントを畑をたがやしはじめる場所にテレポートさせましょう<br>

## 6.エージェントをテレポートさせよう

`||agent.エージェント||`ボタンをクリックしてその中の`||agent.エージェントを…へ西(xのマイナス方向)向きにテレポートさせる||`と書いてあるブロックを`||loops.くりかえし５回||`の上にドラックしてみましょう<br>
`||agent.西(xのマイナス方向)▼||`をクリックして`||agent.東(xのプラス方向)▼||`にしましょう<br>
<img style="width:100%" src="https://i.ibb.co/sWmZSGB/l4-6.gif"><br>
```block
player.onChat("run", function () {
    agent.teleport(pos(0, 0, 0), EAST)
    for (let index = 0; index < 5; index++) {
        agent.setItem(CARROTS, 1, 1)
        agent.till(FORWARD)
        agent.place(FORWARD)
        agent.move(LEFT, 1)
    }
})
```

## 7.座標を入れてみましょう

`||positions.ポジション||`ボタンをクリックしてその中の`||positions.ワールド0 0 0||`を`||agent.~0~0~0||`の上までドラッグします<br>
`||positions.ワールド0 0 0||`を`||positions.ワールド19 -21 -1||`にしましょう<br>
<img style="width:100%" src="https://i.ibb.co/Df9tzFJ/l4-7.gif"><br>
```block
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

## 8.『実行』ボタンをクリックしましょう
画面右下にある緑の『▶』ボタンをクリックして作ったプログラムを実行し、チャットコマンドで`||player.run||`と入力してみましょう<br>