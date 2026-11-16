# ステージの下にマグマを置(お)こう！

```blocks
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
})


```

## ステージの下にマグマを置こう！ @unplugged
絶対座標(ぜったいざひょう)で、カベの形にブロックを並(なら)べよう！<br>
<n></n>
<img style="display: block; margin: auto;" height="50%" width="50%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson9/L9_complete1.png">



## 目標(もくひょう)
``||blocks.ブロックを並べる||``を使って、床(ゆか)をガラスにして、その下にマグマがわくようにしよう！<br>
・チャットコマンドで「set」と入力すると、指定した座標にガラスのカベと床が作られ、その下にマグマがわく<br>
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson9/L9_complete1.png">



## 座標を考えよう
**よこから見た図**で座標を考えよう！<br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson9/L9_1.png">
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson9/L9_2.png">
どこの部分が変(か)わったかよく見て考えよう！<br>



## プログラムを用意する
マグマブロックを並べるコードを用意しよう！<br>
・``||blocks.ブロック||``から``||blocks.ブロックを並べる||``を取り出して、``||player.チャットコマンドsetを入力した時||``にはめ込(こ)む<br>
・ブロックの種類(しゅるい)を**マグマ**にする<br>
・``||positions.ポジション||``から``||positions.ワールド(0, 0, 0)||``を取り出し、範囲(はんい)の始まりと範囲の終わりにはめ込む<br>



## 座標を入力する
下の画像(がぞう)の★の部分に入る座標を、先ほどの図を元にして**自分で考えてプログラミングしよう**！<br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson9/L9_3.png">

```blocks

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
})

```



## 実行しよう！
プログラミングができあがったら、▶ボタンを押(お)して実行しよう<br>
<br></br>
<img height="50%" width="50%" src="https://vcode-esia.com/images_for_world_data/school/1st/execute.gif">
<br></br>
ゲーム画面にもどったら、チャットで「set」と入力してガラスのカベと床、マグマを並べよう<br>
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson9/L9_complete1.png">
<br></br>
できあがったのを確認(かくにん)したら、**ピリジャー？に話しかけよう**<br>