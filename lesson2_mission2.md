# LESSON2 つり場をなおそう

```block
player.onChat("run", function () {
    blocks.fill(
    PLANKS_BIRCH,
    world(685, 64, 804),
    world(687, 64, 806),
    FillOperation.Replace
    )
})
```

```template
player.onChat("run", function () {

})
```

## 目標

まずはこれから作るものの形を確認しよう！<br>
・チャットで「run」と入力したら、こわれているつり場を直すようにプログラミングをする<br>
・ワールド(685, 64, 804)からワールド(687, 64, 806)にブロックを置く<br>
・置くブロックは樺（かば）の板材を使う<br>
<img style="width:100%" src="https://i.ibb.co/kmDrcT6/2.png"><br>

## 1.コードブロックを設置してみましょう

`||blocks.ブロック||`ボタンをクリックしてその中の`||blocks.ブロックを並べる～||`と書いてあるブロックを中央までドラックしてみましょう</br>
`||blocks.土ブロック||`をクリックして`||blocks.樺（かば）の板材||`に変えましょう

```block
player.onChat("run", function () {
    blocks.fill(
    PLANKS_BIRCH,
    pos(0, 0, 0),
    pos(0, 0, 0),
    FillOperation.Replace
    )
})

```

## 2.座標を変更してみましょう

`||positions.ポジション||`ボタンをクリックしてその中の`||positions.ワールド0 0 0||`を`||blocks.範囲の始まり~0~0~0||`の上までドラッグします</br>
`||positions.範囲の始まり ワールド0 0 0||`を`||positions.ワールド685 64 804||`に変えましょう</br>

```block
player.onChat("run", function () {
    blocks.fill(
    PLANKS_BIRCH,
    world(685, 64, 804),
    pos(0, 0, 0),
    FillOperation.Replace
    )
})

```

## 3.座標を変更してみましょう

`||positions.ポジション||`ボタンをクリックしてその中の`||positions.ワールド0 0 0||`を`||blocks.範囲の終わり~0~0~0||`の上までドラッグします</br>
`||positions.範囲の終わり ワールド0 0 0||`を`||positions.ワールド687 64 806||`に変えましょう</br>

```block
player.onChat("run", function () {
    blocks.fill(
    PLANKS_BIRCH,
    world(685, 64, 804),
    world(687, 64, 806),
    FillOperation.Replace
    )
})

```

## 4.『実行』ボタンをクリックしましょう

画面右下にある緑の『▶』ボタンをクリックして作ったプログラムを実行し、チャットコマンドで`||player.run||`と入力してみましょう
