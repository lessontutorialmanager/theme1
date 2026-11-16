# LESSON1 橋を作ってみよう
```block
player.onChat("run", function () {
    blocks.fill(
    PLANKS_OAK,
    world(677, 65, 798),
    world(684, 65, 801),
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
・チャットで「run」と入力したら、穴があいている橋を直すようにプログラミングをする<br>
・ワールド(677, 65, 798)からワールド(684, 65, 801)にブロックを置く<br>
・置くブロックはオークの板材を使う<br>
<img style="width:100%" src="https://i.ibb.co/QfC5mnw/1.png"><br>

## 0.座標を使ってプログラミングしてみよう @unplugged
プログラミングでこわれた橋をかけるプログラムを作ろう！<br>
<img style="display: block; margin: auto;" height="50%" width="90%" src="https://i.ibb.co/yBrQg0P/lesson2-0.png">

## 1.コードブロックを設置してみましょう

`||blocks.ブロック||`ボタンをクリックしてその中の`||blocks.ブロックを並べる～||`と書いてあるブロックを中央までドラックしてみましょう</br>
`||blocks.土ブロック||`をクリックして`||blocks.オークの板材||`に変えましょう
<img style="width:100%" src="https://i.ibb.co/8cHMsw8/lesson2-1.gif">
```block
player.onChat("run", function () {
    blocks.fill(
    PLANKS_OAK,
    pos(0, 0, 0),
    pos(0, 0, 0),
    FillOperation.Replace
    )
})

```

## 2.座標を変更してみましょう

`||positions.ポジション||`ボタンをクリックしてその中の`||positions.ワールド0 0 0||`を`||blocks.範囲の始まり~0~0~0||`の上までドラッグします</br>
`||positions.範囲の始まり ワールド0 0 0||`を`||positions.ワールド677 65 798||`に変えましょう</br>
<img style="width:100%" src="https://i.ibb.co/6RHd3fC/lesson2-2.gif">
```block
player.onChat("run", function () {
    blocks.fill(
    PLANKS_OAK,
    world(677, 65, 798),
    pos(0, 0, 0),
    FillOperation.Replace
    )
})

```

## 3.座標を変更してみましょう

`||positions.ポジション||`ボタンをクリックしてその中の`||positions.ワールド0 0 0||`を`||blocks.範囲の終わり~0~0~0||`の上までドラッグします</br>
`||positions.範囲の終わり ワールド0 0 0||`を`||positions.ワールド684 65 801||`に変えましょう</br>
<img style="width:100%" src="https://i.ibb.co/Jp7WWCH/lesson2-3.gif">
```block
player.onChat("run", function () {
    blocks.fill(
    PLANKS_OAK,
    world(677, 65, 798),
    world(684, 65, 801),
    FillOperation.Replace
    )
})

```
## 4.『実行』ボタンをクリックしましょう
画面右下にある緑の『▶』ボタンをクリックして作ったプログラムを実行し、チャットコマンドで`||player.run||`と入力してみましょう
<img style="width:100%" src="https://i.ibb.co/Xk8v6CY/lesson2-4.gif">