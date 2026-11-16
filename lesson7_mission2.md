```block
player.onChat("run", function () {
    agent.teleport(world(-157, 63, 177), WEST)
    for (let index = 0; index < 9; index++) {
        if (agent.inspect(AgentInspection.Block, FORWARD) == OAK_FENCE) {
            agent.move(RIGHT, 1)
        } else {
            agent.setItem(OAK_FENCE, 1, 1)
            agent.place(FORWARD)
            agent.move(RIGHT, 1)
        }
    }
})
```

```template
player.onChat("run", function () {

})
```

# LESSON6 こわれたフェンスを直そう

## 目標

まずはこれから作るものの形を確認しよう！<br>
・チャットで「run」と入力したら、エージェントがフェンスを置くようにプログラミングをする<br>
・エージェントはフェンスがある場所は右に進み、ない場所はフェンスを置いてから右に進むようにする<br>
・エージェントは初めにワールド-157 63 177、西(xのマイナス方向)にテレポートする<br>
・フェンスはオークのフェンス<br>
<img style="width:100%" src="https://i.ibb.co/0m1n6dS/l6fencel.gif"><br>

## エージェントにフェンスを直してもらおう

Lesson5を思い出してエージェントにフェンスを置かせましょう</br></br>
もし、思い出せないときはえがおの建築士に話しかけて`||agent.【ヒント】||`ボタンを押してからCキーを押してみましょう</br>
