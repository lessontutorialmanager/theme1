```template
player.onChat("run", function () {
    agent.teleport(world(-13, 1, -24), SOUTH)
    for (let index = 0; index < 13; index++) {
        if (agent.inspect(AgentInspection.Block, FORWARD) == WARPED_FENCE) {
            agent.move(RIGHT, 1)
        } else {
            agent.setItem(WARPED_FENCE, 1, 1)
            agent.place(FORWARD)
            agent.move(RIGHT, 1)
        }
    }
})
```

# 学んだプログラムを使ってみよう

## プログラムを自由にくみかえよう
今日、学んだプログラムを見てみましょう<br>
見終わったら`||完了||`をクリックしてすべての使って自由にプログラミングをしてみましょう<br>
<img style="width:100%" src="https://i.ibb.co/Sf6zB2y/finishok.gif"><br>