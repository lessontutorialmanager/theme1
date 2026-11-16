# エージェントに自動で迷路(めいろ)をクリアさせよう！

```blocks

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

```template

player.onChat("run", function () {
})

```

## エージェントに自動で迷路をクリアさせよう！ @unplugged
**左手法(ひだりてほう)**を使ってエージェントに迷路をクリアさせよう<br>
<n></n>
<img style="display: block; margin: auto;" height="50%" width="50%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson10/L10_complete2.gif">



## 目標(もくひょう)
チャットで「run」と入力したら、自動でエージェントがゴールまで進むようにしよう！<br>
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson10/L10_complete2.gif">



## 左手法とは
実は、迷路には**左手法**という**必(かなら)ずゴールに着く方法(ほうほう)**があります！<br>
左手法は以下(いか)のルールで迷路を進みます<br>
・**左**に進めるなら**左**に進む<br>
・左に進めないなら、**前**に進む<br>
・左も前も進めないなら、**右**に進む<br>
・左も前も右も進めないなら、**後ろ**に引き返す<br>
これをゴールまでくり返すと、いつか必ずゴールにたどり着きます！<br>
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson10/L10_4.png">



## ゴールしたかどうかの条件分岐(じょうけんぶんき)
ゴールしたかどうかを確認(かくにん)する条件分岐を用意しよう！<br>
ゴールの足もとには、**金の感圧板(かんあつばん)**があり、それ以外(いがい)の迷路の道は**シーランタン**でできていることから、**エージェントの足もとがシーランタンならくりかえし**となるようにしよう<br>
・``||loops.ループ||``から``||loops.もし～ならくり返し||``を取り出して、``||チャットコマンドrunを入力した時||``にはめ込(こ)む<br>
・``||logic.論理(ろんり)||``から``||logic.0 = 0||``を取り出して条件にはめ込む<br>
・``||agent.エージェント||``から``||agent.エージェントの前のブロック||``を取り出して、``||logic.0 = 0||``の**左**にはめ込み、方向を**下**にする<br>
・``||logic.0 = 0||``の**右側**は、``||blocks.シーランタン||``となるようにする<br>
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson10/L10_5.gif">

```blocks

player.onChat("run", function () {
    while (agent.inspect(AgentInspection.Block, DOWN) == SEA_LANTERN) {
    }
})

```


## エージェントが進む方向の条件分岐
エージェントが進む方向を決める条件分岐を用意しよう！<br>
・**左**に進めるなら**左**に進む<br>
・左に進めないなら、**前**に進む<br>
・左も前も進めないなら、**右**に進む<br>
・左も前も右も進めないなら、**後ろ**に引き返す<br>
という順番(じゅんばん)で条件分岐すれば良(よ)いということが分かっています<br>
左に進める=**エージェントの左にブロックがない**という形で考えましょう！<br>
**自分で考えて条件分岐**しよう！<br>
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson10/L10_4.png">

```blocks

player.onChat("run", function () {
    while (agent.inspect(AgentInspection.Block, DOWN) == SEA_LANTERN) {
        if (!(agent.detect(AgentDetection.Block, LEFT))) {
        } else if (!(agent.detect(AgentDetection.Block, FORWARD))) {
        } else if (!(agent.detect(AgentDetection.Block, RIGHT))) {
        } else {
        }
    }
})

```

## エージェントの動き
それぞれの条件のエージェントの動きを、**自分で考えてプログラミングしよう**<br>
ヒント：「左に進む」は、``||agent.エージェントの向きを左に変える||``と、``||agent.エージェントを1ブロック前に移動(いどう)させる||``を使う<br>
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson10/L10_4.png">

```blocks

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



## 実行しよう！
プログラミングができあがったら、▶ボタンを押して実行しよう<br>
<br></br>
<img height="50%" width="50%" src="https://vcode-esia.com/images_for_world_data/school/1st/execute.gif">
<br></br>
ゲーム画面にもどったら、**村人に話しかけよう！**<br>