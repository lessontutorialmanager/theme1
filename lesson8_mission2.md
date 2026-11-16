# グロウストーンの天井(てんじょう)を作ろう！

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
})

```

## グロウストーンで天井を作ろう！ @unplugged

絶対座標(ぜったいざひょう)で、カベの形にブロックを並(なら)べよう！<br>
<br></br>
<img style="display: block; margin: auto;" height="50%" width="50%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson8/L8_complete2.png">

## 目標(もくひょう)

`||blocks.ブロックを並べる||`使って、カベの上にグロウストーンの天井を作ろう！<br>
・チャットコマンドで「set」と入力すると、指定した座標にガラスのカベが作られ、その上にグロウストーンの天井が作られる<br>
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson8/L8_complete2.png">

## 天井の作り方

天井を作る手順(てじゅん)をかんがえよう！<br>
①上から見た図　大きさは**カベと同じ**<br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson8/L8_11.png">
➁横から見た図　高さはカベの終わりの**3ブロック上**<br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson8/L8_12.png">
これをヒントに座標をかんがえよう！<br>

## 座標の意味

もう一度、座標の意味をおさらいしよう！<br>
座標とは、**東西、上下、南北を3つの数字で表したもの**のことです！<br>
それぞれの数字を変(か)えるとどうなるか、確認(かくにん)しよう！<br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson8/L8_9.png">
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson8/L8_10.png">

## プログラムを用意する

まずはブロックを並べるコードを用意しよう！<br>
・`||blocks.ブロック||`から`||blocks.ブロックを並べる||`を取り出して、`||player.チャットコマンドsetを入力した時||`の**一番下**にはめ込(こ)む<br>
・ブロックの種類(しゅるい)を**グロウストーン**にする<br>
・`||positions.ポジション||`から`||positions.ワールド(0, 0, 0)||`を取り出し、範囲(はんい)の始まりと範囲の終わりにはめ込む<br>

## 座標を入力する

調べたことを元にして、**自分で考えて座標を入力しよう！**<br>

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
})

```

## 実行しよう！

プログラミングができあがったら、▶ボタンを押して実行しよう<br>
<br></br>
<img height="50%" width="50%" src="https://vcode-esia.com/images_for_world_data/school/1st/execute.gif">
<br></br>
ゲーム画面にもどったら、チャットで「set」と入力してガラスのカベとグロウストーンの天井を並べよう<br>
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson8/L8_complete2.png">
<br></br>
できあがったのを確認したら、**ピリジャー？に話しかけよう**<br>
