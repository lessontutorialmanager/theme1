# スノーゴーレムをスポーンさせよう！

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
```

## スノーゴーレムをスポーンさせよう！ @unplugged
鉄の剣(けん)を使ったらスノーゴーレムがスポーンするようにしよう！<br>
<n></n>
<img style="display: block; margin: auto;" height="50%" width="50%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson9/L9_complete2.gif">



## 目標(もくひょう)
``||player.次のアイテムが使われた時||``を使ってイベントを検知(けんち)し、スノーゴーレムをスポーンさせよう！<br>
・チャットコマンドで「set」と入力して、ステージの中に移動(いどう)する<br>
・ステージの中で、**鉄の剣を持って右クリック**して使うと、**スノーゴーレムがスポーン**する<br>
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson9/L9_complete2.gif">



## スノーゴーレムをスポーンさせる方法(ほうほう)
スノーゴーレムは、2つ**雪**を並(なら)べた上に、**くり抜(ぬ)かれたカボチャ**を置(お)くくとスポーンします！<br>
<img width="50%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson9/L9_4.png">
鉄の剣を使うと、**プレイヤーがテレポートする位置(いち)と同じところ**にスノーゴーレムがスポーンするようにしよう！<br>



## プログラムを用意する
ブロックを並べるコードを用意しよう！<br>
・``||player.プレイヤー||``から``||player.次のアイテムが使われた時||``を取り出して、アイテムの種類(しゅるい)を**鉄の剣**にする<br>
・``||blocks.ブロックを並べる||``を取り出して``||player.次のアイテムが使われた時||``にはめ込(こ)み、ブロックの種類を**雪**にする<br>
・``||positions.ポジション||``から``||positions.ワールド(0, 0, 0)||``を取り出し、範囲(はんい)の始まりと範囲の終わりにはめ込む<br>
・``||blocks.ブロックを(~0, ~0, ~0)に置く||``を取り出して``||player.次のアイテムが使われた時||``にはめ込み、ブロックの種類を**くり抜かれたカボチャ**にする<br>
・``||positions.ポジション||``から``||positions.ワールド(0, 0, 0)||``を取り出し、``||positions.(~0, ~0, ~0)||``にはめ込む<br>



## 座標(ざひょう)を入力する
下の画像(がぞう)の★の部分に入る座標を、先ほどの図を元にして**自分で考えてプログラミングしよう**！<br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson9/L9_5.png">

```blocks

player.onItemInteracted(IRON_SWORD, function () {
    blocks.fill(
    SNOW,
    world(1388, 87, -875),
    world(1388, 88, -875),
    FillOperation.Replace
    )
    blocks.place(JACK_O_LANTERN, world(1388, 89, -875))
})

```



## 実行しよう！
プログラミングができあがったら、▶ボタンを押(お)して実行しよう<br>
<br></br>
<img height="50%" width="50%" src="https://vcode-esia.com/images_for_world_data/school/1st/execute.gif">
<br></br>
ゲーム画面にもどったら、チャットで「set」と入力してガラスのカベと床(ゆか)、マグマを並べよう<br>
ステージの中に移動して、鉄の剣を持ったら**右クリックで使用**して**スノーゴーレムを3体スポーン**させよう！<br>
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson9/L9_complete2.gif">