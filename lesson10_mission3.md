# エージェントにより複雑(ふくざつ)な動きをさせよう！

```blocks
player.onChat("run", function () {
    while (agent.inspect(AgentInspection.Block, DOWN) == SEA_LANTERN) {
        if (agent.inspect(AgentInspection.Block, FORWARD) == LEVER) {
            agent.interact(FORWARD)
            agent.move(FORWARD, 1)
        } else if (agent.inspect(AgentInspection.Block, LEFT) == LEVER) {
            agent.turn(LEFT_TURN)
            agent.interact(FORWARD)
            agent.move(FORWARD, 1)
        } else if (agent.inspect(AgentInspection.Block, RIGHT) == LEVER) {
            agent.turn(RIGHT_TURN)
            agent.interact(FORWARD)
            agent.move(FORWARD, 1)
        } else {
            if (!(agent.detect(AgentDetection.Block, LEFT))) {
                agent.turn(LEFT_TURN)
                agent.move(FORWARD, 1)
            } else if (!(agent.detect(AgentDetection.Block, FORWARD))) {
                agent.move(FORWARD, 1)
            } else if (!(agent.detect(AgentDetection.Block, RIGHT))) {
                agent.turn(RIGHT_TURN)
                agent.move(FORWARD, 1)
            } else {
                agent.turn(LEFT_TURN)
                agent.turn(LEFT_TURN)
                agent.move(FORWARD, 1)
            }
        }
    }
})


```


```template

player.onChat("run", function () {
    while (agent.inspect(AgentInspection.Block, DOWN) == SEA_LANTERN) {
        if (!(agent.detect(AgentDetection.Block, LEFT))) {
            agent.turn(LEFT_TURN)
            agent.move(FORWARD, 1)
        } else if (!(agent.detect(AgentDetection.Block, FORWARD))) {
            agent.move(FORWARD, 1)
        } else if (!(agent.detect(AgentDetection.Block, RIGHT))) {
            agent.turn(RIGHT_TURN)
            agent.move(FORWARD, 1)
        } else {
            agent.turn(LEFT_TURN)
            agent.turn(LEFT_TURN)
            agent.move(FORWARD, 1)
        }
    }
})

```

## エージェントにより複雑な動きをさせよう！ @unplugged
レバーを見つけたらインタラクトするようにしよう<br>
<n></n>
<img style="display: block; margin: auto;" height="50%" width="50%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson10/L10_complete3.gif">



## 目標(もくひょう)
チャットで「run」と入力したら、自動でエージェントがゴールまで進むようにしよう！<br>
もしレバーがあるときは、レバーをインタラクト(動かす)させるようにしよう<br>
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson10/L10_complete3.gif">



## 全体の条件分岐(じょうけんぶんき)
先ほど作った**左手法(ひだりてほう)**のプログラムと、レバーの条件分岐がどのようになるか確認(かくにん)しよう！<br>
①先にレバーがあるかどうか確認し、**もしレバーがあるならレバーをインタラクトして前に1ブロック進む**<br>
➁**もしレバーがないなら**、左手法<br>
したがって、先ほど作った条件分岐の**前**にレバーに関(かん)する条件分岐を追加(ついか)しよう！<br>
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson10/L10_6.png">



## 条件分岐の追加
新しく条件分岐を追加しよう！<br>
・``||loops.ループ||``から``||loops.もし～なら でなければ||``を取り出して、``||logic.もしエージェントの左にブロックがあるではないなら||``の**上**にはめ込(こ)む<br>
・⊕を**2回**おす<br>
・**でなければ**の部分に``||logic.もしエージェントの左にブロックがあるではないなら||``の条件分岐をすべて移動(いどう)させる<br>
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson10/L10_7.gif">

```blocks

player.onChat("run", function () {
    while (agent.inspect(AgentInspection.Block, DOWN) == SEA_LANTERN) {
        if () {
        } else if () {
        } else if () {
        } else {
            if (!(agent.detect(AgentDetection.Block, LEFT))) {
                agent.turn(LEFT_TURN)
                agent.move(FORWARD, 1)
            } else if (!(agent.detect(AgentDetection.Block, FORWARD))) {
                agent.move(FORWARD, 1)
            } else if (!(agent.detect(AgentDetection.Block, RIGHT))) {
                agent.turn(RIGHT_TURN)
                agent.move(FORWARD, 1)
            } else {
                agent.turn(LEFT_TURN)
                agent.turn(LEFT_TURN)
                agent.move(FORWARD, 1)
            }
        }
    }
})


```


## 条件を作る
エージェントがレバーを引く条件を作ろう！<br>
①エージェントの**前**にあるブロックが``||blocks.レバー||``なら<br>
➁エージェントの**左**にあるブロックが``||blocks.レバー||``なら<br>
③エージェントの**右**にあるブロックが``||blocks.レバー||``なら<br>
という順番(じゅんばん)で、条件を**自分で考えてプログラミングしよう**<br>

```blocks

player.onChat("run", function () {
    while (agent.inspect(AgentInspection.Block, DOWN) == SEA_LANTERN) {
        if (agent.inspect(AgentInspection.Block, FORWARD) == LEVER) {
        } else if (agent.inspect(AgentInspection.Block, LEFT) == LEVER) {
        } else if (agent.inspect(AgentInspection.Block, RIGHT) == LEVER) {
        } else {
            if (!(agent.detect(AgentDetection.Block, LEFT))) {
                agent.turn(LEFT_TURN)
                agent.move(FORWARD, 1)
            } else if (!(agent.detect(AgentDetection.Block, FORWARD))) {
                agent.move(FORWARD, 1)
            } else if (!(agent.detect(AgentDetection.Block, RIGHT))) {
                agent.turn(RIGHT_TURN)
                agent.move(FORWARD, 1)
            } else {
                agent.turn(LEFT_TURN)
                agent.turn(LEFT_TURN)
                agent.move(FORWARD, 1)
            }
        }
    }
})

```

## エージェントの動き
それぞれの条件のエージェントの動きを、**自分で考えてプログラミングしよう**<br>
ヒント：左にレバーがあるときは、``||agent.エージェントの向きを左に変(か)える||``と、``||agent.エージェントにインタラクトさせる||``、``||agent.エージェントを1ブロック前に移動させる||``を使う<br>
インタラクトさせたあとに、前に1ブロック移動させるのをわすれないようにしよう！<br>
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson10/L10_6.png">

```blocks

player.onChat("run", function () {
    while (agent.inspect(AgentInspection.Block, DOWN) == SEA_LANTERN) {
        if (agent.inspect(AgentInspection.Block, FORWARD) == LEVER) {
            agent.interact(FORWARD)
            agent.move(FORWARD, 1)
        } else if (agent.inspect(AgentInspection.Block, LEFT) == LEVER) {
            agent.turn(LEFT_TURN)
            agent.interact(FORWARD)
            agent.move(FORWARD, 1)
        } else if (agent.inspect(AgentInspection.Block, RIGHT) == LEVER) {
            agent.turn(RIGHT_TURN)
            agent.interact(FORWARD)
            agent.move(FORWARD, 1)
        } else {
            if (!(agent.detect(AgentDetection.Block, LEFT))) {
                agent.turn(LEFT_TURN)
                agent.move(FORWARD, 1)
            } else if (!(agent.detect(AgentDetection.Block, FORWARD))) {
                agent.move(FORWARD, 1)
            } else if (!(agent.detect(AgentDetection.Block, RIGHT))) {
                agent.turn(RIGHT_TURN)
                agent.move(FORWARD, 1)
            } else {
                agent.turn(LEFT_TURN)
                agent.turn(LEFT_TURN)
                agent.move(FORWARD, 1)
            }
        }
    }
})

```



## 実行しよう！
プログラミングができあがったら、▶ボタンを押して実行しよう<br>
<br></br>
<img height="50%" width="50%" src="https://vcode-esia.com/images_for_world_data/school/1st/execute.gif">
<br></br>
ゲーム画面にもどったら、**村人に話しかけよう！**<br>