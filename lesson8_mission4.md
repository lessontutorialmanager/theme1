# ゲームをさらに面白(おもしろ)くしよう！

```blocks
mobs.onMobKilled(mobs.monster(ZOMBIE), function () {
    for (let index = 0; index < 3; index++) {
        mobs.spawn(mobs.monster(ZOMBIE), world(1388, 87, -875))
    }
})
player.onChat("set", function () {
    blocks.fill(
    GLASS,
    world(1383, 87, -880),
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
player.onChat("start", function () {
    mobs.spawn(mobs.monster(ZOMBIE), world(1388, 87, -875))
})
```

```template

mobs.onMobKilled(mobs.monster(ZOMBIE), function () {
    for (let index = 0; index < 3; index++) {
        mobs.spawn(mobs.monster(ZOMBIE), world(1388, 87, -875))
    }
})
player.onChat("set", function () {
    blocks.fill(
    GLASS,
    world(1383, 87, -880),
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
player.onChat("start", function () {
    mobs.spawn(mobs.monster(ZOMBIE), world(1388, 87, -875))
})

```

## ゲームをさらに面白くしよう！@unplugged

工夫(くふう)してゲームをもっと難(むずか)しくしたり面白くしたりしよう！<br>

## 例①

渡(わた)す武器(ぶき)を好(す)きなものに変(か)えてみよう！<br>

## 例➁

出てくるモンスターをもっと強いものに変えてみよう！<br>
モンスターを変えるときは、`||mobs.モンスターをワールド(1388, 87, -875)にスポーンさせる||`だけではなく、`||mobs.モンスターが死んだ時||`も変えるようにしよう！<br>

## 例③

倒(たお)したときに出てくるモンスターの数を増(ふ)やそう！<br>
`||mobs.モンスターが死んだ時||`のくり返しの数を変えて、もっとたくさんのモンスターがスポーンするようにしよう！<br>
