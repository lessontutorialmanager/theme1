# ゲームをより難(むずか)しくしよう！

```blocks
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


```template

mobs.onMobKilled(mobs.monster(ZOMBIE), function () {
    for (let index = 0; index < 3; index++) {
        mobs.spawn(mobs.monster(ZOMBIE), world(1388, 87, -875))
    }
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
    mobs.spawn(mobs.monster(ZOMBIE), world(1388, 87, -875))
})

```

## ゲームをより難しくしよう！ @unplugged
ステージを狭(せま)くしたり、ゾンビがどんどん出てくるようにしたりして、ゲームを楽しくしよう！<br>
<n></n>
<img style="display: block; margin: auto;" height="50%" width="50%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson9/L9_complete3.gif">



## 目標(もくひょう)
時間でゾンビがスポーンするようにしたり、ステージをせまくしたりしよう<br>
・チャットで「start」と入力すると、プレイヤーがマグマに落ちるまで**5秒に1体ゾンビがスポーン**する<br>
・チャットで「start」と入力してから**30秒**後に、ステージをせまくする<br>
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson9/L9_complete3.gif">



## 条件分岐(じょうけんぶんき)とループを考える
ゾンビをくり返しスポーンするしくみを考えよう！<br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson9/L9_6.png">
どんな時にゾンビをスポーンさせるのか、図をなぞりながら考えよう！<br>
**もしプレイヤーが、床(ゆか)より上の位置(いち)にいるならくり返す**とすれば良(よ)さそうです！<br>



## プログラムを用意する
プレイヤーが床より上にいるときにくり返すように、プログラムを用意しよう！<br>
・``||loops.ループ||``から``||loops.もし～ならくりかえし||``を取り出して、``||mobs.ゾンビをワールド(1388, 87, -875)にスポーンさせる||``をはさむ<br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson9/L9_7.gif">
・``||logic.論理(ろんり)||``から``||logic.0 < 0||``を取り出して``||loops.もし～ならくりかえし||``にはめ込(こ)んで、向きを``||logic.0 > 0||``にする<br>
・``||positions.ポジション||``から``||positions.positionのx(東西)座標(ざひょう)||``を取り出し、``||logic.0 > 0||``の**左**にはめ込んで、**y(高低(こうてい))**に変(か)える<br>
・``||player.プレイヤー||``から``||player.プレイヤーの位置||``を取り出して``||positions.positionのx(東西)座標||``のpositionの部分にはめ込む<br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson9/L9_8.gif">




## 床の高さを考える
``||logic.プレイヤーの位置のy(高低)座標 > 0||``の**0**をどんな数字にすれば**床より上なら**という意味になるか、**自分で考えて数字を変えよう**！<br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson9/L9_9.png">

```blocks

player.onChat("start", function () {
    player.runChatCommand("stage")
    while (player.position().getValue(Axis.Y) > 86) {
        mobs.spawn(mobs.monster(ZOMBIE), world(1388, 87, -875))
    }
})

```



## 5秒ごとにくりかえす
ゾンビをスポーン→5秒まつ→ゾンビをスポーン→…というふうに、5秒おきにゾンビがスポーンするようにしよう<br>
・``||loops.一時停止(ていし)(ミリ秒) 100||``を取り出して、``||mobs.ゾンビをワールド(1388, 87, -875)にスポーンさせる||``の下にはめ込む<br>
・数字を**5000**にする<br>
※1秒 = 1000ミリ秒<br>

```blocks

player.onChat("start", function () {
    player.runChatCommand("stage")
    while (player.position().getValue(Axis.Y) > 86) {
        mobs.spawn(mobs.monster(ZOMBIE), world(1388, 87, -875))
        loops.pause(5000)
    }
})

```



## ステージを狭くする
チャットで「start」と入力すると、**30秒**後にステージがせまくなるようにしよう！<br>
まずは下の図を見て、ガラスの床のどの部分を空気に置き換(か)えれば良さそうか考えよう<br>
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson9/L9_10.png">



## プログラムを用意する
ブロックを並(なら)べるコードを用意しよう！<br>
・``||player.プレイヤー||``から``||player.チャットコマンドjumpを入力した時||``を取り出して、チャットを**stage**にする<br>
・``||blocks.ブロックを並べる||``を取り出して``||player.チャットコマンドstageを入力した時||``にはめ込み、ブロックを**空気**にする<br>
・``||positions.ポジション||``から``||positions.ワールド(0, 0, 0)||``を取り出し、範囲(はんい)の始まりと範囲の終わりにはめ込む<br>
同じように、``||blocks.ブロックを並べる||``を**4つ**用意しよう！<br>



## 座標を入力する
下の図を元にして、4つの``||blocks.ブロックを並べる||``の範囲の始まりと範囲の終わりを**自分で考えてプログラミングしよう**！<br>
高さは**86**にしよう<br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson9/L9_10.png">

```blocks

player.onChat("stage", function () {
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

```



## 30秒まつ
30秒経(た)ってからステージがせまくなるように、``||loops.一時停止(ミリ秒) 100||``を使おう！<br>
・``||loops.ループ||``から``||loops.一時停止(ミリ秒) 100||``を取り出し、``||player.チャットコマンドstageを入力した時||``の**一番上**にはめ込む<br>
・時間を**30000**にする<br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson9/L9_11.gif">

```blocks

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

```

## startのときにstageも実行する
チャットを「start」「stage」と2回入力するのはめんどうなので、**「start」と入力した時に「stage」も実行されるようにしよう！**<br>
・``||player.プレイヤー||``から``||player.チャットコマンドjumpを実行する||``を取り出し、``||player.チャットコマンドstartを入力した時||``の**一番上**にはめ込む<br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson9/L9_12.gif">

```blocks
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


## 実行しよう！
プログラミングができあがったら、▶ボタンを押(お)して実行しよう<br>
<br></br>
<img height="50%" width="50%" src="https://vcode-esia.com/images_for_world_data/school/1st/execute.gif">
<br></br>
ゲーム画面にもどったら、チャットで「set」と入力して戦(たたか)いの準備(じゅんび)をしよう<br>
準備ができたら、チャットで「start」と入力してゲームに挑戦(ちょうせん)しよう！<br>
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson9/L9_complete3.gif">
ゲームが終わったら**ピリジャー？に話しかけよう！**<br>