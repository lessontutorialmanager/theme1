```block
player.onChat("run", function () {
    blocks.fill(
    IRON_BLOCK,
    world(-152, 62, 176),
    world(-146, 67, 182),
    FillOperation.Hollow
    )
    blocks.fill(
    GLASS,
    world(-150, 64, 182),
    world(-148, 65, 182),
    FillOperation.Replace
    )
    blocks.fill(
    GLASS,
    world(-150, 64, 176),
    world(-148, 65, 176),
    FillOperation.Replace
    )
    blocks.place(IRON_DOOR, world(-152, 63, 179))
})
```

```template
player.onChat("run", function () {
	
})
```

# LESSON3 倉庫を作ってみよう

## 目標
まずはこれから作るものの形を確認しよう！<br>
・チャットで「run」と入力したら、四角い建物ができて、前面にドア、左右にまどができるようにプログラミングをする<br>
・倉庫の範囲の始まりはワールド-152 62 176、範囲の終わりはワールド-146 67 182にする<br>
・右側のまどの範囲の始まりはワールド-150 64 182、範囲の終わりはワールド-148 65 182にする<br>
・左側のまどの範囲の始まりはワールド-150 64 176、範囲の終わりはワールド-148 65 176にする<br>
・ドアはワールド-152 63 179に置く<br>
・倉庫は鉄ブロック、ドアは鉄のドア、まどはガラスブロックで作る<br>
<img style="width:100%" src="https://i.ibb.co/M5G3FXz/3.png"><br>

## 鉄ブロックで倉庫を作ってみよう
Lesson3を思い出して鉄ブロックで倉庫を作ってみましょう</br>
ドアは鉄のドア、倉庫の左右にはガラスブロックで縦２ブロック・横３ブロックのまどを作りましょう</br></br>
もし、思い出せないときはうきうきしている村人に話しかけて`||agent.【ヒント】||`ボタンを押してからCキーを押してみましょう</br>