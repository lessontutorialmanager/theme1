# ガラスのカベを作ろう！

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
})

```

```template

player.onChat("set", function () {

})

```

## ガラスのカベを作ろう！ @unplugged

絶対座標(ぜったいざひょう)で、カベの形にブロックを並(なら)べよう！<br>
<n></n>
<img style="display: block; margin: auto;" height="50%" width="50%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson8/L8_complete1.gif">

## 目標(もくひょう)

`||blocks.ブロックを並べる||`をうまく使って、カベを作ろう！<br>
・チャットコマンドで「set」と入力すると、指定した座標にガラスのカベが作られる<br>
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson8/L8_complete1.gif">

## カベの作り方

**上から見た図**でカベを作る手順(てじゅん)をかんがえよう！<br>
①ガラスを四角い形に並べる<br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson8/L8_1.png">
➁ガラスの一番外側(そとがわ)だけのこるように、空気ブロックで中をくりぬく<br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson8/L8_2.png">
こうすれば、カベの形にガラスを置(お)くことができそうです！<br>

## 座標の意味

ここで、座標の意味をおさらいしよう！<br>
座標とは、**東西、上下、南北を3つの数字で表したもの**のことです！<br>
それぞれの数字を変(か)えるとどうなるか、確認(かくにん)しよう！<br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson8/L8_9.png">
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson8/L8_10.png">

## プログラムを用意する

まずはブロックを並べるコードを用意しよう！<br>
・`||blocks.ブロック||`から`||blocks.ブロックを並べる||`を取り出して、`||player.チャットコマンドsetを入力した時||`にはめ込(こ)む<br>
・ブロックの種類(しゅるい)を**ガラス**にする<br>
・`||positions.ポジション||`から`||positions.ワールド(0, 0, 0)||`を取り出し、範囲(はんい)の始まりと範囲の終わりにはめ込む<br>
・同じように、**空気**ブロックも並べられるように用意する<br>
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson8/L8_3.gif">
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson8/L8_4.png">

## ガラスの範囲の始まりを調べる

ガラスを並べる座標の、**範囲の始まり**を調べよう！<br>
・プログラミングの画面を閉(と)じて、**ダイヤモンドのブロック**の上に立つ<br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson8/L8_5.gif">
・画面の左上の**位置(いち)**に書かれた座標を調べる<br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson8/L8_6.png">
・`||blocks.ブロックを並べる||`の**範囲の始まり**に調べた座標を入力する<br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson8/L8_7.png">

## ガラスの範囲の終わりを調べる

同じように、ガラスを並べる座標の、**範囲の終わり**を調べよう！<br>
・プログラミングの画面を閉じて、**エメラルドのブロック**の上に立つ<br>
・画面の左上の**位置**に書かれた座標を調べる<br>
・`||blocks.ブロックを並べる||`の**範囲の終わり**に調べた座標を入力する<br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson8/L8_7.png">

## ガラスの中をくりぬく

次に、**空気**ブロックでガラス内側をくりぬくようにしよう！<br>
ガラスブロックの中をくりぬくためには、下の図の範囲の始まりと範囲の終わりの座標が必要です<br>
先ほどと同じように調べて、**範囲の始まり**と**範囲の終わり**に入力しよう！<br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson8/L8_8.png">

## 高さを入力する

今回は、**高さ**を下のように入力しよう！<br>
範囲の始まり：87<br>
範囲の終わり：90<br>

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
})

```

## 実行しよう！

プログラミングができあがったら、▶ボタンを押(お)して実行しよう<br>
<br></br>
<img height="50%" width="50%" src="https://vcode-esia.com/images_for_world_data/school/1st/execute.gif">
<br></br>
ゲーム画面にもどったら、チャットで「set」と入力してガラスのカベを並べよう<br>
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson8/L8_complete1.gif">
<br></br>
できあがったのを確認したら、**ピリジャー？に話しかけよう**<br>
