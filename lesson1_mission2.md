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

# LESSON2 キノコシチューを出してみよう

## 目標
まずはこれから作るプログラムを確認しよう！<br>
・チャットで「run」と入力したら、プレイヤーにキノコシチューを３つわたすようにプログラミングをする<br>
<img style="width:100%" src="https://i.ibb.co/tmJf60H/2024-03-15-103219.png"><br>

## 1.コードブロックを設置してみましょう

`||mobs.モブ||`をクリックしてその中の`||mobs.次の対象～||`と書いてあるブロックを中央までドラックしてみましょう

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

`||mobs.次の対象～||`ブロックの`||mobs.対象：一番近いプレイヤー(@p)||`をクリックして設定を`||mobs.自分(@s)||`に変えましょう

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
ドラックしたら`||blocks.シャベル||`をクリックして`||blocks.キノコシチュー||`に変えましょう

```blocks
player.onChat("run", function () {
    mobs.give(
    mobs.target(LOCAL_PLAYER),
    MUSHROOM_STEW,
    1
    )
})

```

## 4.個数を変更してみましょう
`||mobs.次の対象～||`ブロックの個数を`||mobs.１つ||`から`||mobs.３つ||`に変えましょう

```blocks
player.onChat("run", function () {
    mobs.give(
    mobs.target(LOCAL_PLAYER),
    MUSHROOM_STEW,
    3
    )
})

```

## 5.『実行』ボタンをクリックしましょう
画面右下にある緑の『▶』ボタンをクリックして作ったプログラムを実行して、遭難者に話しかけてみよう


