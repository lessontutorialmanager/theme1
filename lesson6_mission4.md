```block
player.onChat("run", function () {
    agent.teleport(world(22, -21, -1), WEST)
    agent.setItem(CARROTS, 25, 1)
    for (let index = 0; index < 5; index++) {
        for (let index = 0; index < 5; index++) {
            agent.till(FORWARD)
            agent.place(FORWARD)
            agent.move(LEFT, 1)
        }
        agent.move(BACK, 1)
        agent.move(RIGHT, 6)
    }
})
```

```template
player.onChat("run", function () {
	
})
```

# LESSON4 畑を作ってみよう

## 目標
まずはこれから作るものの形を確認しよう！<br>
・チャットで「run」と入力したら、エージェントがたて５ブロック、横５ブロックの畑を作るようにプログラミングをする<br>
・エージェントは初めにワールド-164 63 170、西(xのマイナス方向)にテレポートする<br>
・畑にニンジンを植える<br>
<img style="width:100%" src="https://i.ibb.co/m4RFwzg/4.png"><br>

## エージェントを使って畑を作ってみよう
Lesson4を思い出してエージェントを使って畑を作ってみましょう</br></br>
もし、思い出せないときはうきうきしている村人に話しかけて`||agent.【ヒント】||`ボタンを押してからCキーを押してみましょう</br>