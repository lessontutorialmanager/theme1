# ゲームの仕組みを作ろう！

```blocks
mobs.onMobKilled(mobs.monster(ZOMBIE), function () {
    player.say("ゾンビをたおした！")
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
})

```

## ゲームの仕組みを作ろう！@unplugged

イベントとループを使ってゲームの仕組みを作ろう！<br>
<br></br>
<img style="display: block; margin: auto;" height="50%" width="50%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson8/L8_complete3.gif">

## 目標(もくひょう)

イベントとループを使って、ゾンビをたおすゲームを作ろう！<br>
①ゲームの準備(じゅんび)をするしくみ<br>
・チャットで「set」と入力すると、プレイヤーが**ワールド(1388, 87, -875)**にテレポートし、**鉄の剣(けん)**と**盾(たて)**をわたして、難易度(なんいど)を**ノーマル**にする<br>
➁ゲームをはじめるしくみ<br>
・チャットで「start」と入力すると、**ゾンビ**を**ワールド(1388, 87, -875)**にスポーンさせる<br>
③ゲーム中のしくみ<br>
・ゾンビが死んだら、ゾンビを**3体**スポーンさせる<br>
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson8/L8_complete3.gif">

## ①ゲームの準備をするしくみ

チャットで「set」と入力した時のプログラムを作ろう！<br>
・`||player.プレイヤー||`から`||player.(~0, ~0, ~0)にテレポートする||`を取り出して、`||player.チャットコマンドsetを入力した時||`にはめ込(こ)む<br>
・`||positions.ワールド(1388, 87, -875)||`にテレポートするように**自分で考えて設定(せってい)**する<br>
・`||mobs.アイテムを与(あた)える||`と`||blocks.アイテム||`を組み合わせて、**鉄の剣**と**盾**を**自分**に渡(わた)すように**自分で考えて設定**する<br>

## ①ゲームの準備をするしくみ

ゾンビがスポーンできるようにゲームの難易度を変えよう！<br>
・`||gameplay.ゲームプレイ||`から`||gameplay.ゲームの難易度を～に変更(へんこう)する||`を取り出して、`||player.チャットコマンドsetを入力した時||`にはめ込む<br>
難易度を**ノーマル**にする<br>
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson8/L8_13.gif">

```blocks

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


```

## ➁ゲームをはじめるしくみ

チャットで「start」と入力した時、**ゾンビ**が1体スポーンするようにしよう！<br>
・`||player.プレイヤー||`から`||player.チャットコマンドjumpを入力した時||`を取り出して、jumpを**start**に変(か)える<br>
・`||mobs.モブ||`から`||mobs.生き物を(~0, ~0, ~0)にスポーンさせる||`を取り出して、`||player.チャットコマンドstartを入力した時||`にはめ込む<br>
・`||mobs.モブ||`から`||mobs.モンスター||`を取り出して、`||mobs.生き物を(~0, ~0, ~0)にスポーンさせる||`にはめ込む<br>
・`||positions.ワールド(1388, 87, -875)||`にスポーンするように**自分で考えて設定する**<br>
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson8/L8_14.gif">

```blocks

player.onChat("start", function () {
    mobs.spawn(mobs.monster(ZOMBIE), world(1388, 87, -875))
})

```

## ③ゲーム中のしくみ

ゾンビが死んだ時、新たに**ゾンビが3体**スポーンするようにしよう！<br>
・`||mobs.モブ||`から`||mobs.生き物が死んだ時||`を取り出す<br>
・`||mobs.モブ||`から`||mobs.モンスター||`を取り出して、`||mobs.生き物が死んだ時||`にはめ込む<br>
・`||positions.ワールド(1388, 87, -875)||`に**ゾンビ**が**3体**スポーンするように**自分で考えて設定する**<br>
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson8/L8_14.gif">

```blocks

mobs.onMobKilled(mobs.monster(ZOMBIE), function () {
    for (let index = 0; index < 3; index++) {
        mobs.spawn(mobs.monster(ZOMBIE), world(1388, 87, -875))
    }
})

```

## 実行しよう！

プログラミングができあがったら、▶ボタンを押して実行しよう<br>
<br></br>
<img height="50%" width="50%" src="https://vcode-esia.com/images_for_world_data/school/1st/execute.gif">
<br></br>
ゲーム画面にもどったら、チャットで「set」と入力して、戦(たたか)いの準備をしよう<br>
準備ができたら、チャットで「start」と入力してゾンビと戦おう！ゾンビはどんどん増(ふ)えていくので注意しよう！<br>
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson8/L8_complete3.gif">
<br></br>
死んでしまったら、**ピリジャー？に話しかけよう**<br>
