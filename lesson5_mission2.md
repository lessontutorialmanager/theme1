# LESSON2 砂ブロックを草ブロックに置きかえよう
```block
player.onChat("run", function () {
    agent.teleport(world(-19, 1, -21), SOUTH)
    for (let index = 0; index < 13; index++) {
        if (agent.inspect(AgentInspection.Block, DOWN) == SAND) {
            agent.setItem(GRASS, 1, 1)
            agent.destroy(DOWN)
            agent.place(DOWN)
            agent.move(FORWARD, 1)
        } else {
            agent.move(FORWARD, 1)
        }
    }
})
```

```template
player.onChat("run", function () {
    agent.teleport(world(-19, 1, -21), SOUTH)
    for (let index = 0; index < 12; index++) {
        if (agent.inspect(AgentInspection.Block, FORWARD) == LOG_OAK) {
            agent.destroy(FORWARD)
            agent.move(FORWARD, 1)
        } else {
            agent.move(FORWARD, 1)
        }
    }
})
```

## 目標
先ほど作ったプログラムを改造（かいぞう）して、砂を草ブロックにしよう！<br>
・チャットで「run」と入力したら、エージェントに砂ブロックをこわして草ブロックをおくようにプログラミングをする<br>
・エージェントははじめにワールド-19 1 -21、南(zのプラス方向)にテレポートする<br>
・エージェントの下に砂ブロックがあればこわしてから草ブロックをおいてすすみ、ないときはすすむだけとする<br>
<img style="width:100%" src="https://i.ibb.co/92tVH9v/l5-q2-all.gif"><br>

## 原木をこわしたプログラムを使って、プログラムを作ろう
まずは原木をこわしたプログラムを使って、砂ブロックをこわしてもらいましょう<br>
<img style="width:100%" src="https://i.ibb.co/WVXswp7/l5-suna-kowasu.gif"><br>

## 1.条件分岐（じょうけんぶんき）の条件（じょうけん）をかえてみましょう

砂ブロックはエージェントの下にあるので、エージェントにかくにんしてもらう場所を【前】から【下】にします<br>
<img style="width:90%" src="https://i.ibb.co/44NSM26/if.png">の`||agent.前▼||`をクリックして、`||agent.下▼||`にしましょう<br>
<img style="width:20%" src="https://i.ibb.co/vwMhYMp/pg1block.png">オークの原木をクリックして<img style="width:20%" src="https://i.ibb.co/rHmHfky/pg2block.png">砂ブロックにしましょう<br>

```block
player.onChat("run", function () {
    agent.teleport(world(-19, 1, -21), SOUTH)
    for (let index = 0; index < 12; index++) {
        if (agent.inspect(AgentInspection.Block, DOWN) == SAND) {
            agent.destroy(FORWARD)
            agent.move(FORWARD, 1)
        } else {
            agent.move(FORWARD, 1)
        }
    }
})

```

## 2.エージェントに下にある砂ブロックをこわしてもらいましょう

砂ブロックは下にあるので、エージェントにこわしてもらう場所も【下】にしましょう<br>
`||agent.エージェントに前を破壊（はかい）させる||`の`||agent.前▼||`をクリックして、`||agent.下▼||`にしましょう<br>

```block
player.onChat("run", function () {
    agent.teleport(world(-19, 1, -21), SOUTH)
    for (let index = 0; index < 12; index++) {
        if (agent.inspect(AgentInspection.Block, DOWN) == SAND) {
            agent.destroy(DOWN)
            agent.move(FORWARD, 1)
        } else {
            agent.move(FORWARD, 1)
        }
    }
})

```

## 草ブロックをおいてもらおう
下に砂ブロックがあるときにこわすプログラムができました<br>
しかし、このままではブロックをこわして穴があいたまま、すすんでしまいます<br>
次のページからあいた穴に草ブロックをおいてから、すすむようにしましょう<br>
<img style="width:100%;" src="https://i.ibb.co/XtC7q9F/l5-suna-kowasu-susumu.gif"><br>
<img style="display: block; margin: 0 auto; width: 25%;" src="https://i.ibb.co/SKKzwsC/sita.png"><br>
<img style="width:100%" src="https://i.ibb.co/ck6MRFf/l5-aru-kowasiteoku-suna.gif"><br>

## 3.エージェントに草ブロックをわたしましょう

`||agent.エージェント||`ボタンをクリックしてその中の`||agent.エージェントに…を１個、自分のスロット１番に設定させる||`と書いてあるブロックを`||agent.エージェントに下を破壊させる||`の上にドラックしてみましょう<br>

```block
player.onChat("run", function () {
    agent.teleport(world(-19, 1, -21), SOUTH)
    for (let index = 0; index < 12; index++) {
        if (agent.inspect(AgentInspection.Block, DOWN) == SAND) {
            agent.setItem(GRASS, 1, 1)
            agent.destroy(DOWN)
            agent.move(FORWARD, 1)
        } else {
            agent.move(FORWARD, 1)
        }
    }
})

```

## 4.エージェントにブロックをおいてもらいましょう

`||agent.エージェント||`ボタンをクリックしてその中の`||agent.エージェントに前へ置かせる||`と書いてあるブロックを`||agent.エージェントに下を破壊させる||`の下にドラックしてみましょう<br>
`||agent.前▼||`をクリックして`||agent.下▼||`に変えましょう<br>

```block
player.onChat("run", function () {
    agent.teleport(world(-19, 1, -21), SOUTH)
    for (let index = 0; index < 12; index++) {
        if (agent.inspect(AgentInspection.Block, DOWN) == SAND) {
            agent.setItem(GRASS, 1, 1)
            agent.destroy(DOWN)
            agent.place(DOWN)
            agent.move(FORWARD, 1)
        } else {
            agent.move(FORWARD, 1)
        }
    }
})

```

## 5.くりかえしの数をかえましょう

`||loops.くりかえし１２回||`を`||１３回||`にしましょう<br>


```block
player.onChat("run", function () {
    agent.teleport(world(-19, 1, -21), SOUTH)
    for (let index = 0; index < 13; index++) {
        if (agent.inspect(AgentInspection.Block, DOWN) == SAND) {
            agent.setItem(GRASS, 1, 1)
            agent.destroy(DOWN)
            agent.place(DOWN)
            agent.move(FORWARD, 1)
        } else {
            agent.move(FORWARD, 1)
        }
    }
})

```

## 6.『実行』ボタンをクリックしましょう
画面右下にある緑の『▶』ボタンをクリックして作ったプログラムを実行し、チャットコマンドで`||player.run||`と入力してみましょう