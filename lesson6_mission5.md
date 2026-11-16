```template
player.onChat("run1", function () {
    mobs.give(
    mobs.target(LOCAL_PLAYER),
    DIAMOND_PICKAXE,
    1
    )
})
player.onChat("run2", function () {
    blocks.fill(
    LIGHT_GRAY_CONCRETE,
    world(-166, 62, 176),
    world(-160, 62, 182),
    FillOperation.Replace
    )
})
player.onChat("run3", function () {
    blocks.fill(
    IRON_BLOCK,
    world(-152, 62, 176),
    world(-146, 67, 182),
    FillOperation.Hollow
    )
    blocks.fill(
    GLASS,
    world(-150, 64, 182),
    world(-148, 65, 182),
    FillOperation.Replace
    )
    blocks.fill(
    GLASS,
    world(-150, 64, 176),
    world(-148, 65, 176),
    FillOperation.Replace
    )
    blocks.place(IRON_DOOR, world(-152, 63, 179))
})
player.onChat("run4", function () {
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

# 学んだプログラムを使ってみよう

## プログラムを自由にくみかえよう
今日、学んだプログラムを見てみましょう<br>
見終わったら`||完了||`をクリックしてすべての使って自由にプログラミングをしてみましょう<br>
<img style="width:100%" src="https://i.ibb.co/Sf6zB2y/finishok.gif"><br>