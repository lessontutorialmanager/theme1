# イベントを検知(けんち)してジャンプ力をアップしよう！

```blocks

player.onTravelled(SWIM_WATER, function () {
    player.say("海に落ちた！")
    player.teleport(world(-412, 65, 1309))
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

```

## イベントを検知してジャンプ力をアップしよう！ @unplugged
プレイヤーがバウンドしたときにジャンプ力が上がるようにしよう<br>
<n></n>
<img style="display: block; margin: auto;" height="50%" width="50%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson11/L11_complete2.gif">



## 目標(もくひょう)
プレイヤーのジャンプ力をアップさせよう！<br>
・**プレイヤーがバウンドした**というイベントを検知して、プレイヤーのジャンプ力をアップさせる<br>
・チャットで「go」と入力すると、飛(と)びこみ台の上にテレポートするようにする<br>
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson11/L11_complete2.gif">



## イベントの検知
プレイヤーがバウンドしたというイベントを検知しよう！<br>
・``||player.プレイヤー||``から``||player.プレイヤーが歩いた時||``を取り出し、**バウンドした時**に変更(へんこう)する<br>
・``||mobs.モブ||``から``||mobs.一番近いプレイヤー(@p)に効果(こうか)時間10効果レベル1の～を与(あた)える||``を取り出し、``||player.プレイヤーがバウンドした時||``にはめ込(こ)む<br>
・効果を与える相手を**自分(@s)**にし、効果レベルを**25**にする<br>
・効果の種類(しゅるい)を**跳躍力(ちょうやくりょく)上昇(じょうしょう)**にする<br>
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson11/L11_4.png">

```blocks

player.onTravelled(BOUNCE, function () {
    mobs.applyEffect(JUMP_BOOST, mobs.target(LOCAL_PLAYER), 10, 25)
})

```



## プレイヤーをテレポートさせる
チャットで「go」と入力したら、飛びこみ台の上にテレポートするよう**自分で考えてプログラミングしよう**！<br>
``||positions.ワールド(0, 0, 0)||``を使うことを忘(わす)れないようにしよう！<br>
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson11/L11_3.png">

```blocks

player.onTravelled(SWIM_WATER, function () {
    player.say("海に落ちた！")
    player.teleport(world(-412, 65, 1309))
})

```



## 実行しよう！
プログラミングができあがったら、▶ボタンを押(お)して実行しよう<br>
<br></br>
<img height="50%" width="50%" src="https://vcode-esia.com/images_for_world_data/school/1st/execute.gif">
<br></br>
ゲーム画面にもどったら、チャットで「go」と入力して、飛びこみ台の上に行こう！<br>
飛びこみ台の上からトランポリンに落ちると、ジャンプ力がアップします！<br>
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson11/L11_complete2.gif">
大ジャンプして、**Y座標(ざひょう)が100以上の高さまでとぼう！**<br>