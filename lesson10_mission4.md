# ゲームをもっと楽しくしよう！

```blocks
player.onItemInteracted(STICK, function () {
    mobs.applyEffect(SPEED, mobs.target(LOCAL_PLAYER), 10, 6)
})
player.onChat("run", function () {
    while (agent.inspect(AgentInspection.Block, DOWN) == SEA_LANTERN) {
        agent.destroy(DOWN)
        agent.setItem(GLOWSTONE, 1, 1)
        agent.place(DOWN)
        if (agent.inspect(AgentInspection.Block, FORWARD) == LEVER) {
            agent.interact(FORWARD)
            agent.move(FORWARD, 1)
        } else if (agent.inspect(AgentInspection.Block, LEFT) == LEVER) {
            agent.turn(LEFT_TURN)
            agent.interact(FORWARD)
            agent.move(FORWARD, 1)
        } else if (agent.inspect(AgentInspection.Block, RIGHT) == LEVER) {
            agent.turn(RIGHT_TURN)
            agent.interact(FORWARD)
            agent.move(FORWARD, 1)
        } else {
            if (!(agent.detect(AgentDetection.Block, LEFT))) {
                agent.turn(LEFT_TURN)
                agent.move(FORWARD, 1)
            } else if (!(agent.detect(AgentDetection.Block, FORWARD))) {
                agent.move(FORWARD, 1)
            } else if (!(agent.detect(AgentDetection.Block, RIGHT))) {
                agent.turn(RIGHT_TURN)
                agent.move(FORWARD, 1)
            } else {
                agent.turn(LEFT_TURN)
                agent.turn(LEFT_TURN)
                agent.move(FORWARD, 1)
            }
        }
    }
})
player.onChat("come", function () {
    agent.teleport(pos(0, 0, 0), positions.toCompassDirection(player.getOrientation()))
})
mobs.give(
mobs.target(LOCAL_PLAYER),
STICK,
1
)





```


```template

player.onChat("run", function () {
    while (agent.inspect(AgentInspection.Block, DOWN) == SEA_LANTERN) {
        if (agent.inspect(AgentInspection.Block, FORWARD) == LEVER) {
            agent.interact(FORWARD)
            agent.move(FORWARD, 1)
        } else if (agent.inspect(AgentInspection.Block, LEFT) == LEVER) {
            agent.turn(LEFT_TURN)
            agent.interact(FORWARD)
            agent.move(FORWARD, 1)
        } else if (agent.inspect(AgentInspection.Block, RIGHT) == LEVER) {
            agent.turn(RIGHT_TURN)
            agent.interact(FORWARD)
            agent.move(FORWARD, 1)
        } else {
            if (!(agent.detect(AgentDetection.Block, LEFT))) {
                agent.turn(LEFT_TURN)
                agent.move(FORWARD, 1)
            } else if (!(agent.detect(AgentDetection.Block, FORWARD))) {
                agent.move(FORWARD, 1)
            } else if (!(agent.detect(AgentDetection.Block, RIGHT))) {
                agent.turn(RIGHT_TURN)
                agent.move(FORWARD, 1)
            } else {
                agent.turn(LEFT_TURN)
                agent.turn(LEFT_TURN)
                agent.move(FORWARD, 1)
            }
        }
    }
})

```

## ゲームをもっと楽しくしよう！ @unplugged
ゲームをもっと楽しくしよう！<br>



## 例(れい)①
エージェントが迷路を解いている様子を、ついていって確認しよう！<br>
エージェントが動く前に、エージェントの足もとのブロックを壊(こわ)させて、グロウストーンを置(お)かせれば、エージェントがどこを通ったかわかりやすくなります！<br>

```blocks

player.onChat("run", function () {
    while (agent.inspect(AgentInspection.Block, DOWN) == SEA_LANTERN) {
        agent.destroy(DOWN)
        agent.setItem(GLOWSTONE, 1, 1)
        agent.place(DOWN)
        if (agent.inspect(AgentInspection.Block, FORWARD) == LEVER) {
            agent.interact(FORWARD)
            agent.move(FORWARD, 1)
        } else if (agent.inspect(AgentInspection.Block, LEFT) == LEVER) {
            agent.turn(LEFT_TURN)
            agent.interact(FORWARD)
            agent.move(FORWARD, 1)
        } else if (agent.inspect(AgentInspection.Block, RIGHT) == LEVER) {
            agent.turn(RIGHT_TURN)
            agent.interact(FORWARD)
            agent.move(FORWARD, 1)
        } else {
            if (!(agent.detect(AgentDetection.Block, LEFT))) {
                agent.turn(LEFT_TURN)
                agent.move(FORWARD, 1)
            } else if (!(agent.detect(AgentDetection.Block, FORWARD))) {
                agent.move(FORWARD, 1)
            } else if (!(agent.detect(AgentDetection.Block, RIGHT))) {
                agent.turn(RIGHT_TURN)
                agent.move(FORWARD, 1)
            } else {
                agent.turn(LEFT_TURN)
                agent.turn(LEFT_TURN)
                agent.move(FORWARD, 1)
            }
        }
    }
})
player.onChat("come", function () {
    agent.teleport(pos(0, 0, 0), positions.toCompassDirection(player.getOrientation()))
})

```

## 例➁
エージェントについていけるようにプレイヤーの移動速度(いどうそくど)を上げよう！<br>
プレイヤーに棒(ぼう)をわたし、棒を使った時に移動速度が上がるようにしよう！<br>

```blocks

mobs.give(
mobs.target(LOCAL_PLAYER),
STICK,
1
)
player.onItemInteracted(STICK, function () {
    mobs.applyEffect(SPEED, mobs.target(LOCAL_PLAYER), 10, 6)
})

```

