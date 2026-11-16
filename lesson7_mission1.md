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
<img style="width:100%" src="https://i.ibb.co/SvzCP5g/iswall.gif"><br>

## エージェントに家のかべを作ってもらいましょう

Lesson4を思い出してアイテムをプログラミングで出してみましょう</br></br>
もし、思い出せないときはうきうきしている村人に話しかけて`||agent.【ヒント】||`ボタンを押してからCキーを押してみましょう</br>
