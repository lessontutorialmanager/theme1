# エージェントを操作(そうさ)しよう！

```blocks
player.onItemInteracted(IRON_SHOVEL, function () {
    agent.turn(LEFT_TURN)
})
player.onItemInteracted(STICK, function () {
    while (!(agent.detect(AgentDetection.Block, FORWARD))) {
        agent.move(FORWARD, 1)
        if (!(agent.detect(AgentDetection.Block, RIGHT))) {
            player.say("右")
            break;
        } else if (!(agent.detect(AgentDetection.Block, LEFT))) {
            player.say("左")
            break;
        }
    }
})
mobs.give(
mobs.target(LOCAL_PLAYER),
STICK,
1
)
mobs.give(
mobs.target(LOCAL_PLAYER),
IRON_SHOVEL,
1
)




```


## エージェントを操作しよう！ @unplugged
アイテムを使ってエージェントを操作しよう！<br>
<n></n>
<img style="display: block; margin: auto;" height="50%" width="50%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson10/L10_complete1.gif">



## 目標(もくひょう)
アイテムを使って、エージェントを動かそう！<br>
・**鉄のシャベル**を使うと、エージェントが左を向く<br>
・**棒(ぼう)**を使うと、エージェントが曲がり道を見つけるまで前に進む<br>
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson10/L10_complete1.gif">



## プレイヤーにアイテムを渡(わた)す
プログラムを実行したときに、プレイヤーに**鉄のシャベル**と**棒**を渡すように、**自分で考えてプログラミングしよう**<br>
ヒント：``||loops.最初(さいしょ)だけ||``を使う<br>

```blocks

mobs.give(
mobs.target(LOCAL_PLAYER),
STICK,
1
)
mobs.give(
mobs.target(LOCAL_PLAYER),
IRON_SHOVEL,
1
)

```



## イベントを検知(けんち)する
鉄のシャベルを使った、棒を使ったというイベントを検知するためのコードを**自分で考えて取り出そう**<br>

```blocks

player.onItemInteracted(IRON_SHOVEL, function () {
})
player.onItemInteracted(STICK, function () {
})

```



## エージェントを左に向ける
鉄のシャベルを使った時に、エージェントが左を向くように**自分で考えてプログラミングしよう**<br>

```blocks

player.onItemInteracted(IRON_SHOVEL, function () {
    agent.turn(LEFT_TURN)
})

```



## 条件分岐(じょうけんぶんき)を考える
棒を使った時の条件分岐を考えよう！<br>
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson10/L10_1.png">
・エージェントの前に**ブロックがない**とき、**くり返しエージェントが前に1ブロック進む**<br>
・1ブロック進んだ後に、**もしエージェントの右にブロックがなければ**、「右」とメッセージを送ってくり返しを止める<br>
・エージェントの右にブロックがあるのを確認(かくにん)した上で、**もしエージェントの左にブロックがなければ**、「左」とメッセージを送ってくり返しを止める<br>


## 条件分岐①
エージェントの**前**にブロックがあるかどうか確認しよう<br>
・``||loops.ループ||``から``||loops.もし～ならくりかえし||``を取り出して、``||player.棒が使われた時||``にはめ込(こ)む<br>
・``||logic.論理(ろんり)||``から``||logic.～ではない||``を取り出して、``||loops.もし～ならくりかえし||``にはめ込む<br>
・``||agent.エージェント||``から``||agent.エージェントの前にブロックがある||``を取り出して、``||logic.～ではない||``にはめ込む<br>
これで、**エージェントの前にブロックがないならくりかえす**という条件分岐ができました！<br>
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson10/L10_2.gif">



## 条件分岐➁
エージェントの**左右**にブロックがあるかどうか確認しよう<br>
・``||logic.論理||``から``||logic.もし～なら でなければ||``を取り出して、``||loops.もし～ならくりかえし||``にはめ込む<br>
・``||logic.もし～なら でなければ||``の**⊕を1回押(お)したあと、⊖を押す**<br>
・1つ目の条件に、**エージェントの右にブロックがないなら**となるようにプログラムを作る<br>
・2つ目の条件に、**エージェントの左にブロックがないなら**となるようにプログラムを作る<br>
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson10/L10_3.gif">

```blocks

player.onItemInteracted(STICK, function () {
    while (!(agent.detect(AgentDetection.Block, FORWARD))) {
        if (!(agent.detect(AgentDetection.Block, RIGHT))) {
        } else if (!(agent.detect(AgentDetection.Block, LEFT))) {
        }
    }
})

```


## エージェントの行動を考える
それぞれの条件でのエージェントの行動を、**自分で考えてプログラミングしよう**<br>
・エージェントを動かしたいとき：``||agent.エージェントを前に1ブロック移動(いどう)させる||``を使う<br>
・メッセージを送りたいとき：``||player.メッセージ～を送信(そうしん)する||``を使う<br>
・プログラムを終了したいとき：``||loops.くりかえしを終わる||``を使う<br>
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson10/L10_1.png">

```blocks

player.onItemInteracted(STICK, function () {
    while (!(agent.detect(AgentDetection.Block, FORWARD))) {
        agent.move(FORWARD, 1)
        if (!(agent.detect(AgentDetection.Block, RIGHT))) {
            player.say("右")
            break;
        } else if (!(agent.detect(AgentDetection.Block, LEFT))) {
            player.say("左")
            break;
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