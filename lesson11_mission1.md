# トランポリンと飛(と)びこみ台を作ろう！

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

```

```template

player.onChat("run", function () {
})

```


## トランポリンと飛びこみ台を作ろう！ @unplugged
ブロックを並(なら)べてトランポリンと飛びこみ台を作ろう<br>
<n></n>
<img style="display: block; margin: auto;" height="50%" width="50%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson11/L11_complete1.gif">



## 目標(もくひょう)
ブロックを並べてトランポリンと飛びこみ台を作ろう！<br>
・チャットで「run」と入力すると、トランポリンと飛びこみ台ができる<br>
・トランポリンは**オークの板材(いたざい)**と**スライムブロック**を使う<br>
・飛びこみ台は**柱状(ちゅうじょう)のクォーツのブロック**を使う<br>
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson11/L11_complete1.gif">



## 座標(ざひょう)を考える
まずはそれぞれの座標を考えよう！<br>
<br></br>
①横から見た図<br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson11/L11_1.png">
<br></br>
➁上から見た図<br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson11/L11_2.png">



## ブロックを並べる
``||blocks.ブロックを並べる||``と``||blocks.ブロックを(~0, ~0, ~0)に置(お)く||``、``||positions.ワールド(0, 0, 0)||``を使ってトランポリンと飛びこみ台を作ろう！<br>
先ほどの図をもとにして、``||player.チャットコマンドrunを入力した時||``の中に**自分で考えてプログラミングしよう**<br>

```blocks

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

## イベントを検知(けんち)する
プレイヤーが水の中に落ちたときに、トランポリンの上にテレポートするようにしよう！<br>
・``||player.プレイヤー||``から``||player.プレイヤーが歩いた時||``を取り出し、**水の中を泳いだ時**に変更(へんこう)する<br>
・``||player.プレイヤー||``から``||player.メッセージ～を送信(そうしん)する||``を取り出し、``||player.プレイヤーが水の中を泳いだ時||``にはめ込(こ)む<br>
・メッセージの内容(ないよう)を、**海に落ちた！**にする<br>
・``||player.プレイヤー||``から``||player.(~0, ~0, ~0)にテレポートする||``を取り出し、``||player.プレイヤーが水の中を泳いだ時||``にはめ込む<br>
・テレポートする位置(いち)を、``||positions.ワールド(-412, 65, 1309)||``にする<br>
※``||positions.ワールド(0, 0, 0)||``を使うことに注意！<br>

```blocks

player.onTravelled(SWIM_WATER, function () {
    player.say("海に落ちた！")
    player.teleport(world(-412, 65, 1309))
})

```




## 実行しよう！
プログラミングができあがったら、▶ボタンを押して実行しよう<br>
<br></br>
<img height="50%" width="50%" src="https://vcode-esia.com/images_for_world_data/school/1st/execute.gif">
<br></br>
チャットで「run」と入力して、トランポリンと飛びこみ台を作ろう！<br>
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson11/L11_complete1.gif">
建物(たてもの)ができたら、**かいほうてきな村人に話しかけよう！**<br>