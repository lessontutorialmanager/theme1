# LESSON2 コンクリートで穴をうめよう
```block
player.onChat("run", function () {
    blocks.fill(
    LIGHT_GRAY_CONCRETE,
    world(-166, 62, 176),
    world(-160, 62, 182),
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
・チャットで「run」と入力したら、穴をブロックでうめるようにプログラミングをする<br>
・範囲の始まりはワールド-166 62 176、範囲の終わりはワールド-160 62 182にする<br>
・薄灰色のコンクリートで作る<br>
`||players.次のページから作り方を確認しましょう||`<br>
<img style="width:100%" src="https://i.ibb.co/wLWvpjh/2.png"><br>

## 1.コードブロックを設置してみましょう

`||blocks.ブロック||`ボタンをクリックしてその中の`||blocks.ブロックを並べる～||`と書いてあるブロックを中央までドラックしてみましょう</br>
`||blocks.土ブロック||`をクリックして`||blocks.薄灰色のコンクリート||`に変えましょう

## 2.座標を変更してみましょう

`||positions.ポジション||`ボタンをクリックしてその中の`||positions.ワールド0 0 0||`を`||blocks.範囲の始まり~0~0~0||`の上までドラッグします</br>
`||positions.範囲の始まり ワールド0 0 0||`を`||positions.ワールド-166 62 176||`に変えましょう</br>

## 3.座標を変更してみましょう

`||positions.ポジション||`ボタンをクリックしてその中の`||positions.ワールド0 0 0||`を`||blocks.範囲の終わり~0~0~0||`の上までドラッグします</br>
`||positions.範囲の終わり ワールド0 0 0||`を`||positions.ワールド-160 62 182||`に変えましょう</br>

## 4.『実行』ボタンをクリックしましょう
画面右下にある緑の『▶』ボタンをクリックして作ったプログラムを実行し、チャットコマンドで`||player.run||`と入力してみましょう
```block
player.onChat("run", function () {
    blocks.fill(
    LIGHT_GRAY_CONCRETE,
    world(-166, 62, 176),
    world(-160, 62, 182),
    FillOperation.Replace
    )
})
```