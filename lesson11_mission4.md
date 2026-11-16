# 魔法(まほう)のじゅうたんで帰ろう！

```blocks
player.onTravelled(SWIM_WATER, function () {
    player.say("海に落ちた！")
    player.teleport(world(-412, 65, 1309))
})
player.onTravelled(FALL, function () {
    blocks.fill(
    SLIME_BLOCK,
    positions.groundPosition(posCamera(-2, -1, -1)),
    positions.groundPosition(posCamera(2, -1, 2)),
    FillOperation.Replace
    )
})
player.onTravelled(SPRINT, function () {
    if (blocks.testForBlock(AIR, pos(0, -1, 0))) {
        blocks.fill(
        LIGHT_BLUE_CARPET,
        posCamera(-2, -1, -1),
        posCamera(2, -1, 2),
        FillOperation.Replace
        )
    }
})
player.onChat("run", function () {
    blocks.fill(
    PLANKS_OAK,
    world(-413, 63, 1308),
    world(-411, 63, 1310),
    FillOperation.Replace
    )
    blocks.fill(
    SLIME_BLOCK,
    world(-413, 64, 1308),
    world(-411, 64, 1310),
    FillOperation.Replace
    )
    blocks.fill(
    PILLAR_QUARTZ_BLOCK,
    world(-409, 63, 1309),
    world(-409, 93, 1309),
    FillOperation.Replace
    )
    blocks.place(PILLAR_QUARTZ_BLOCK, world(-410, 93, 1309))
})
player.onTravelled(BOUNCE, function () {
    mobs.applyEffect(JUMP_BOOST, mobs.target(LOCAL_PLAYER), 10, 25)
})
player.onChat("go", function () {
    player.teleport(world(-410, 94, 1309))
})






```


```template

player.onTravelled(SWIM_WATER, function () {
    player.say("海に落ちた！")
    player.teleport(world(-412, 65, 1309))
})
player.onTravelled(SNEAK, function () {
    if (positions.groundPosition(posCamera(2, 8, 12)).getValue(Axis.Y) > 62) {
        player.say("そこは海じゃない！")
    } else {
        player.say("新しい島だ！")
        blocks.fill(
        STONE,
        posCamera(-2, 8, 8),
        positions.groundPosition(posCamera(2, 8, 12)),
        FillOperation.Replace
        )
    }
})
player.onChat("run", function () {
    blocks.fill(
    PLANKS_OAK,
    world(-413, 63, 1308),
    world(-411, 63, 1310),
    FillOperation.Replace
    )
    blocks.fill(
    SLIME_BLOCK,
    world(-413, 64, 1308),
    world(-411, 64, 1310),
    FillOperation.Replace
    )
    blocks.fill(
    PILLAR_QUARTZ_BLOCK,
    world(-409, 63, 1309),
    world(-409, 93, 1309),
    FillOperation.Replace
    )
    blocks.place(PILLAR_QUARTZ_BLOCK, world(-410, 93, 1309))
})
player.onTravelled(BOUNCE, function () {
    mobs.applyEffect(JUMP_BOOST, mobs.target(LOCAL_PLAYER), 10, 25)
})
player.onChat("go", function () {
    player.teleport(world(-410, 94, 1309))
})
player.onTravelled(WALK, function () {
    if (blocks.testForBlock(STONE, pos(0, -1, 0))) {
        blocks.place(SLIME_BLOCK, pos(0, -1, 0))
    }
})

```

## 帰りは魔法のじゅうたんで帰ろう！ @unplugged
ゲームをもっと楽しくしよう！<br>



## 例(れい)①
プレイヤーが走っているというイベントを検知(けんち)して、もしプレイヤーの足もとにブロックがない(空気ブロック)なら、プレイヤーの1ブロック下にカーペットを並(なら)べて、空中を走ろう！<br>

```blocks

player.onTravelled(SPRINT, function () {
    if (blocks.testForBlock(AIR, pos(0, -1, 0))) {
        blocks.fill(
        LIGHT_BLUE_CARPET,
        posCamera(-2, -1, -1),
        posCamera(2, -1, 2),
        FillOperation.Replace
        )
    }
})

```

## 例➁
最後(さいご)はジャンプして安全に着地！<br>
プレイヤーが落下しているというイベントを検知して、プレイヤーの下の地面の座標(ざひょう)にスライムブロックのトランポリンを並べよう！<br>

```blocks

player.onTravelled(FALL, function () {
    blocks.fill(
    SLIME_BLOCK,
    positions.groundPosition(posCamera(-2, -1, -1)),
    positions.groundPosition(posCamera(2, -1, 2)),
    FillOperation.Replace
    )
})

```

