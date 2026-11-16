```template
player.onChat("run", function () {
    agent.teleport(world(-7, -21, 0), SOUTH)
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 4; index++) {
            for (let index = 0; index < 7; index++) {
                agent.setItem(PLANKS_ACACIA, 1, 1)
                agent.place(FORWARD)
                agent.move(LEFT, 1)
            }
            agent.move(UP, 1)
            agent.move(RIGHT, 7)
        }
        agent.move(DOWN, 4)
        agent.move(LEFT, 8)
        agent.move(FORWARD, 1)
        agent.turn(RIGHT_TURN)
    }
})
```

# 学んだプログラムを使ってみよう

## プログラムを自由にくみかえよう
今日、学んだプログラムを見てみましょう<br>
見終わったら`||完了||`をクリックしてすべての使って自由にプログラミングをしてみましょう<br>
<img style="width:100%" src="https://i.ibb.co/Sf6zB2y/finishok.gif"><br>