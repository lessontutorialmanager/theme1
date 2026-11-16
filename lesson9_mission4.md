# ゲームをもっと楽しくしよう！

```blocks
player.onDied(function () {
    gameplay.title(mobs.target(LOCAL_PLAYER), "ゲームオーバー！", "また挑戦してね！")
})
mobs.onMobKilled(mobs.monster(ZOMBIE), function () {
    for (let index = 0; index < 3; index++) {
        mobs.spawn(mobs.monster(ZOMBIE), world(1388, 87, -875))
    }
    mobs.applyEffect(REGENERATION, mobs.target(LOCAL_PLAYER), 5, 1)
})
player.onChat("stage", function () {
    loops.pause(30000)
    blocks.fill(
    AIR,
    world(1383, 86, -880),
    world(1384, 86, -870),
    FillOperation.Replace
    )
    blocks.fill(
    AIR,
    world(1392, 86, -880),
    world(1393, 86, -870),
    FillOperation.Replace
    )
    blocks.fill(
    AIR,
    world(1383, 86, -880),
    world(1393, 86, -879),
    FillOperation.Replace
    )
    blocks.fill(
    AIR,
    world(1383, 86, -871),
    world(1393, 86, -870),
    FillOperation.Replace
    )
})
player.onChat("set", function () {
    blocks.fill(
    GLASS,
    world(1383, 86, -880),
    world(1393, 90, -870),
    FillOperation.Replace
    )
    blocks.fill(
    AIR,
    world(1384, 87, -879),
    world(1392, 90, -871),
    FillOperation.Replace
    )
    blocks.fill(
    GLOWSTONE,
    world(1383, 93, -880),
    world(1393, 93, -870),
    FillOperation.Replace
    )
    blocks.fill(
    LAVA,
    world(1383, 84, -880),
    world(1393, 85, -870),
    FillOperation.Replace
    )
    player.teleport(world(1388, 87, -875))
    mobs.give(
    mobs.target(LOCAL_PLAYER),
    IRON_SWORD,
    1
    )
    mobs.give(
    mobs.target(LOCAL_PLAYER),
    SHIELD,
    1
    )
    gameplay.setDifficulty(NORMAL)
})
player.onItemInteracted(IRON_SWORD, function () {
    blocks.fill(
    SNOW,
    world(1388, 87, -875),
    world(1388, 88, -875),
    FillOperation.Replace
    )
    blocks.place(JACK_O_LANTERN, world(1388, 89, -875))
})
player.onChat("start", function () {
    player.runChatCommand("stage")
    gameplay.title(mobs.target(LOCAL_PLAYER), "ゲームスタート！", "ゾンビをたおそう！")
    while (player.position().getValue(Axis.Y) > 86) {
        mobs.spawn(mobs.monster(ZOMBIE), world(1388, 87, -875))
        loops.pause(5000)
    }
})




```


```template

mobs.onMobKilled(mobs.monster(ZOMBIE), function () {
    for (let index = 0; index < 3; index++) {
        mobs.spawn(mobs.monster(ZOMBIE), world(1388, 87, -875))
    }
})
player.onChat("stage", function () {
    loops.pause(30000)
    blocks.fill(
    AIR,
    world(1383, 86, -880),
    world(1384, 86, -870),
    FillOperation.Replace
    )
    blocks.fill(
    AIR,
    world(1392, 86, -880),
    world(1393, 86, -870),
    FillOperation.Replace
    )
    blocks.fill(
    AIR,
    world(1383, 86, -880),
    world(1393, 86, -879),
    FillOperation.Replace
    )
    blocks.fill(
    AIR,
    world(1383, 86, -871),
    world(1393, 86, -870),
    FillOperation.Replace
    )
})
player.onChat("set", function () {
    blocks.fill(
    GLASS,
    world(1383, 86, -880),
    world(1393, 90, -870),
    FillOperation.Replace
    )
    blocks.fill(
    AIR,
    world(1384, 87, -879),
    world(1392, 90, -871),
    FillOperation.Replace
    )
    blocks.fill(
    GLOWSTONE,
    world(1383, 93, -880),
    world(1393, 93, -870),
    FillOperation.Replace
    )
    blocks.fill(
    LAVA,
    world(1383, 84, -880),
    world(1393, 85, -870),
    FillOperation.Replace
    )
    player.teleport(world(1388, 87, -875))
    mobs.give(
    mobs.target(LOCAL_PLAYER),
    IRON_SWORD,
    1
    )
    mobs.give(
    mobs.target(LOCAL_PLAYER),
    SHIELD,
    1
    )
    gameplay.setDifficulty(NORMAL)
})
player.onItemInteracted(IRON_SWORD, function () {
    blocks.fill(
    SNOW,
    world(1388, 87, -875),
    world(1388, 88, -875),
    FillOperation.Replace
    )
    blocks.place(JACK_O_LANTERN, world(1388, 89, -875))
})
player.onChat("start", function () {
    player.runChatCommand("stage")
    while (player.position().getValue(Axis.Y) > 86) {
        mobs.spawn(mobs.monster(ZOMBIE), world(1388, 87, -875))
        loops.pause(5000)
    }
})

```

## ゲームをもっと楽しくしよう！ @unplugged
ゲームをもっと楽しくしよう！<br>



## 例(れい)①
``||mobs.モブ||``にある``||mobs.一番近いプレーヤー(@p)に持続(じぞく)時間10効果(こうか)レベル1の～を与(あた)える||``を使うと、**プレイヤーに攻撃力(こうげきりょく)アップなどの特殊効果(とくしゅこうか)をつけられます！**<br>
ゾンビを倒(たお)した時に特殊効果がつくようにしよう！<br>

```blocks

mobs.onMobKilled(mobs.monster(ZOMBIE), function () {
    for (let index = 0; index < 3; index++) {
        mobs.spawn(mobs.monster(ZOMBIE), world(1388, 87, -875))
    }
    mobs.applyEffect(REGENERATION, mobs.target(LOCAL_PLAYER), 5, 1)
})

```

## 例➁
``||gameplay.ゲームプレイ||``にある``||gameplay.一番近いプレーヤー(@p)にタイトル～サブタイトル～を表示(ひょうじ)する||``を使うと、**画面に大きく文字を表示できます！**<br>
チャットで「start」と入力した時に、「ゲームスタート！」とタイトルを表示しよう！<br>

```blocks

player.onChat("start", function () {
    player.runChatCommand("stage")
    gameplay.title(mobs.target(LOCAL_PLAYER), "ゲームスタート！", "ゾンビをたおそう！")
    while (player.position().getValue(Axis.Y) > 86) {
        mobs.spawn(mobs.monster(ZOMBIE), world(1388, 87, -875))
        loops.pause(5000)
    }
})

```


## 例③
``||player.プレイヤー||``にある``||player.プレイヤーが死んだ時||``を使うと、**モンスターにやられたりマグマに落ちて死んだというイベントを検知(けんち)できます！**<br>
プレイヤーが死んだ時に、「ゲームオーバー！」とタイトルを表示しよう！<br>

```blocks

player.onDied(function () {
    gameplay.title(mobs.target(LOCAL_PLAYER), "ゲームオーバー！", "また挑戦してね！")
})

```
