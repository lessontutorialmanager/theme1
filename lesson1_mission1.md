# LESSON1 パンを出してみよう

```block
player.onChat("run", function () {
    mobs.give(
    mobs.target(LOCAL_PLAYER),
    BREAD,
    5
    )
})
```

```template
player.onChat("run", function () {
	
})
```

## 目標
まずはこれから作るプログラムを確認しよう！<br>
・チャットで「run」と入力したら、プレイヤーにパンを５つわたすようにプログラミングをする<br>
<img style="width:100%" src="https://i.ibb.co/09WGRpX/2024-03-15-103140.png"><br>

## プログラミングでアイテムを出してみよう！ @unplugged
プログラミングでパンを５つ出して遭難者に渡してあげよう！<br>
<img style="display: block; margin: auto;" height="50%" width="50%" src="https://i.ibb.co/JkrgWy8/lesson1-0.gif">

## 1.コードブロックを設置してみましょう

`||mobs.モブ||`をクリックしてその中の`||mobs.次の対象～||`と書いてあるブロックを中央までドラックしてみましょう
<img style="width:100%" src="https://i.ibb.co/zGXtSJq/lesson1-1.gif">

```blocks
player.onChat("run", function () {
    mobs.give(
    mobs.target(NEAREST_PLAYER),
    GRASS,
    1
    )
})

```

## 2.対象を変更してみましょう

`||mobs.次の対象～||`の`||mobs.対象：一番近いプレイヤー(@p)||`をクリックして設定を`||mobs.自分(@s)||`に変えましょう
<img style="width:100%" src="https://i.ibb.co/VmBSgXJ/lesson1-2.gif">

```blocks
player.onChat("run", function () {
    mobs.give(
    mobs.target(LOCAL_PLAYER),
    GRASS,
    1
    )
})

```

## 3.アイテムを変更してみましょう
`||blocks.ブロック||`をクリックして、その中の`||blocks.アイテム||`と書いてあるブロックを土ブロックの上まで
ドラックします</br>
ドラックしたら`||blocks.シャベル||`をクリックして`||blocks.パン||`に変えましょう
<img style="width:100%" src="https://i.ibb.co/Sv3hPZT/lesson1-3.gif">

```blocks
player.onChat("run", function () {
    mobs.give(
    mobs.target(LOCAL_PLAYER),
    BREAD,
    1
    )
})

```

## 4.個数を変更してみましょう
`||mobs.次の対象～||`の個数を`||mobs.１つ||`から`||mobs.５つ||`に変えましょう
<img style="width:100%" src="https://i.ibb.co/Df5mVCr/lesson1-4.gif">
```blocks
player.onChat("run", function () {
    mobs.give(
    mobs.target(LOCAL_PLAYER),
    BREAD,
    5
    )
})

```

## 5.『実行』ボタンをクリックしましょう
画面右下にある緑の『▶』ボタンをクリックして作ったプログラムを実行して、遭難者に話しかけてみよう
<img style="width:100%" src="https://i.ibb.co/w6YFpgF/lesson1-5.gif">

