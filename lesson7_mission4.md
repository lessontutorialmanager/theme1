```template
player.onChat("run1", function () {
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
player.onChat("run2", function () {
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
player.onChat("run3", function () {
    blocks.fill(
    BRICKS,
    world(-165, 66, 177),
    world(-161, 66, 181),
    FillOperation.Replace
    )
    blocks.fill(
    BRICKS,
    world(-165, 67, 178),
    world(-161, 67, 180),
    FillOperation.Replace
    )
    blocks.fill(
    BRICKS,
    world(-165, 68, 179),
    world(-161, 68, 179),
    FillOperation.Replace
    )
    agent.teleport(world(-166, 67, 176), SOUTH)
    for (let index = 0; index < 3; index++) {
        for (let index = 0; index < 7; index++) {
            agent.setItem(BLACKSTONE, 1, 1)
            agent.place(DOWN)
            agent.move(LEFT, 1)
        }
        agent.move(RIGHT, 7)
        agent.move(FORWARD, 1)
        agent.move(UP, 1)
    }
    agent.teleport(world(-166, 67, 182), SOUTH)
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 7; index++) {
            agent.setItem(BLACKSTONE, 1, 1)
            agent.place(DOWN)
            agent.move(LEFT, 1)
        }
        agent.move(RIGHT, 7)
        agent.move(BACK, 1)
        agent.move(UP, 1)
    }
})
```

# 学んだプログラムを使ってみよう

## プログラムを自由にくみかえよう
今日、学んだプログラムを見てみましょう<br>
見終わったら`||完了||`をクリックしてすべての使って自由にプログラミングをしてみましょう<br>
<img style="width:100%" src="https://i.ibb.co/Sf6zB2y/finishok.gif"><br>