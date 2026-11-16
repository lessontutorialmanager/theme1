# ゴールまでジャンプしよう！

```blocks
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
player.onTravelled(BOUNCE, function () {
    mobs.applyEffect(JUMP_BOOST, mobs.target(LOCAL_PLAYER), 10, 25)
})
player.onChat("go", function () {
    player.teleport(world(-410, 94, 1309))
})

```

## ゴールまでジャンプしよう！ @unplugged
足場を作りながら大ジャンプして、ゴールにむかおう！<br>
<n></n>
<img style="display: block; margin: auto;" height="50%" width="50%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson11/L11_complete3.gif">



## 目標(もくひょう)
プレイヤーのイベントを検知(けんち)して、さまざまなことをできるようにしよう！<br>
・プレイヤーがスニークすると、海に石の足場ができる<br>
・石ブロックの上を歩くと、石がスライムブロックに変(か)わり、ジャンプできるようになる<br>
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson11/L11_complete3.gif">


## イベントを検知する
プレイヤーがスニークしたときに、海の中に島ができるようにしよう！<br>
・``||player.プレイヤー||``から``||player.プレイヤーが歩いた時||``を取り出し、**スニークした時**に変更(へんこう)する<br>
・``||player.プレイヤー||``から``||player.メッセージ～を送信(そうしん)する||``を取り出し、``||player.プレイヤーがスニークした時||``にはめ込(こ)む<br>
・メッセージの内容(ないよう)を、**新しい島だ！**にする<br>
・``||blocks.ブロック||``から``||blocks.ブロックを並(なら)べる||``を取り出し、``||player.プレイヤーがスニークした時||``にはめ込み、ブロックの種類(しゅるい)を**石**にする<br>



## プレイヤーの前に島を作る
これまで、座標(ざひょう)を使うときは**東西**や**南北に注意してきました**<br>
しかし、それだと**プレイヤーが向いている方向を変えても同じ場所に建物(たてもの)ができてしまう**という問題がありました<br>
そこで今回は、``||positions.(右 0, 上 0, 前 0)||``を使いましょう！<br>
これを使うと、**プレイヤーが今見ている部分が正面となる**ため、どの方角を向いていてもプログラムを使うことができます！<br>
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson11/L11_7.png">
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson11/L11_6.gif">



## 座標を考える
今回はプレイヤーの**2ブロック左(-2ブロック右)、8ブロック上、8ブロック前**から並べ始めよう！<br>
・``||positions.ポジション||``から``||positions.(右 0, 上 0, 前 0)||``を取り出して、``||blocks.ブロックを並べる||``の**範囲(はんい)の始まり**にはめ込む<br>
・座標を``||positions.(右 -2, 上 8, 前 8)||``にする<br>
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson11/L11_8.gif">



## 範囲の終わり
範囲の終わりを用意するときに**コピー機能(きのう)**をつかって、下のように設定(せってい)しよう！<br>
・``||positions.ポジション||``から``||positions.(~0, ~0, ~0)の地面||``を取り出して、``||blocks.ブロックを並べる||``の**範囲の終わり**にはめ込む<br>
・先ほど作った``||positions.(右 -2, 上 8, 前 8)||``を**コピー**する<br>
※コピーのやり方：作ったコードを**右クリック**または**長タップ**して、**複製(ふくせい)する**をえらぶ<br>
・コピーした``||positions.(右 -2, 上 8, 前 8)||``を``||positions.(~0, ~0, ~0)の地面||``にはめ込む<br>
・数字を``||positions.(右 2, 上 8, 前 12)||``に変える<br>
<br></br>
コピーのしかた<br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson11/L11_9.gif">
こうすると、石ブロックの足場が、**地面につくまで自動でのびてくれます！**<br>

```blocks

player.onTravelled(SNEAK, function () {
        player.say("新しい島だ！")
        blocks.fill(
        STONE,
        posCamera(-2, 8, 8),
        positions.groundPosition(posCamera(2, 8, 12)),
        FillOperation.Replace
        )
})

```




## 条件分岐(じょうけんぶんき)を考える
足場を作る場所が、水の中かどうか、どうやって条件分岐すれば良(よ)いでしょうか？<br>
先ほど説明(せつめい)したとおり、足場の石ブロックは、**地面につくまで下にのびていきます**<br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson11/L11_10.png">
足場が**水の中**にできるときは、**足場の一番下は、村のある陸地(りくち)のY座標(高さ)よりも下になります**<br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson11/L11_11.png">
足場が**村の陸地**にできるときは、**足場の一番下は、村のある陸地のY座標(高さ)よりも上になります**<br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson11/L11_12.png">
このことから、**足場の一番下の部分のY座標が、村の陸地のY座標62より上かどうか**で場合分けすれば良さそうです！<br>



## 条件分岐を作る①
先ほど考えたことにしたがって条件分岐しよう！<br>
・``||logic.論理(ろんり)||``から``||logic.もし～ならば でなければ||``を取り出し、``||player.プレイヤーがスニークした時||``の**一番上**にはめ込む<br>
・``||player.メッセージ～を送信する||``と``||blocks.ブロックを並べる||``を**でなければ**に移動(いどう)させる<br>
・条件に``||logic.0 < 0||``をはめ込み、記号を``||logic.0 > 0||``に変える<br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson11/L11_13.gif">



## 条件分岐を作る➁
・``||positions.ポジション||``から``||positions.positionのx(東西)座標||``を取り出し、``||logic.0 > 0||``の**左**にはめ込む<br>
・``||positions.(右 2, 上 8, 前 12)の地面||``を**コピー**して、``||positions.positionのx(東西)座標||``の**position**にはめ込み、**y(高低)座標**にする<br>
・``||logic.(右 2, 上 8, 前 12)の地面のy(高低)座標||``の**右**を**62**にする<br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson11/L11_14.gif">


## メッセージ送信する
足場の地面のY座標が62より大きいとき、「そこは海じゃない！」とメッセージ送信しよう！<br>
・``||player.プレイヤー||``から``||player.メッセージ～を送信する||``を取り出し、条件分岐にはめ込む<br>
・メッセージの内容を、**そこは海じゃない！**にする<br>

```blocks

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

```


## プレイヤーの足もとで条件分岐する
プレイヤーが歩いた時、プレイヤーの足もとのブロックが石なら、スライムブロックに置き換(か)えるよう**自分で考えてプログラミングしよう！**<br>

```blocks

player.onTravelled(WALK, function () {
    if (blocks.testForBlock(STONE, pos(0, -1, 0))) {
        blocks.place(SLIME_BLOCK, pos(0, -1, 0))
    }
})

```




## 実行しよう！
プログラミングができあがったら、▶ボタンを押(お)して実行しよう<br>
<br></br>
<img height="50%" width="50%" src="https://vcode-esia.com/images_for_world_data/school/1st/execute.gif">
<br></br>
ゴールの方を向いてスニークし、足場を作ろう！<br>
足場ができたらそこに向かってジャンプし、足場を歩き回って次のトランポリンを作ろう！<br>
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson11/L11_complete3.gif">
はたしてゴールにたどり着けるかな？<br>