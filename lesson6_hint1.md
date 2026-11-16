```block
player.onChat("run", function () {
    mobs.give(
    mobs.target(LOCAL_PLAYER),
    DIAMOND_PICKAXE,
    1
    )
})
```

```template
player.onChat("run", function () {
	
})
```

# LESSON1 ダイヤモンドのツルハシを出してみよう

## 目標
まずはこれから作るものの形を確認しよう！<br>
・チャットで「run」と入力したら、プレイヤーにダイヤモンドのツルハシをわたすようにプログラミングをする<br>
`||players.次のページから作り方を確認しましょう||`<br>
<img style="width:100%" src="https://i.ibb.co/2SCQ3sY/2024-03-08-095646.png"><br>

## 1.コードブロックを設置してみましょう

`||mobs.モブ||`をクリックしてその中の`||mobs.次の対象～||`と書いてあるブロックを中央までドラックしてみましょう

## 2.対象を変更してみましょう

`||mobs.次の対象～||`ブロックの`||mobs.対象：一番近いプレイヤー(@p)||`をクリックして設定を`||mobs.自分(@s)||`に変えましょう

## 3.アイテムを変更してみましょう
`||blocks.ブロック||`をクリックして、その中の`||blocks.アイテム||`と書いてあるブロックを土ブロックの上まで
ドラックします</br>
ドラックしたら`||blocks.シャベル||`をクリックして`||blocks.ダイヤモンドのツルハシ||`に変えましょう

## 4.『実行』ボタンをクリックしましょう
画面右下にある緑の『▶』ボタンをクリックして作ったプログラムを実行して、たくましい大工に話しかけてみよう
```block
player.onChat("run", function () {
    mobs.give(
    mobs.target(LOCAL_PLAYER),
    DIAMOND_PICKAXE,
    1
    )
})
```