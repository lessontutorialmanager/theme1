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

# LESSON2 コンクリートで穴をうめよう

## 目標
まずはこれから作るものの形を確認しよう！<br>
・チャットで「run」と入力したら、穴をブロックでうめるようにプログラミングをする<br>
・範囲の始まりはワールド-166 62 176、範囲の終わりはワールド-160 62 182にする<br>
・薄灰色のコンクリートで作る<br>
<img style="width:100%" src="https://i.ibb.co/wLWvpjh/2.png"><br>

## 薄灰色のコンクリートで穴をうめよう
Lesson2を思い出してブロックで穴をうめましょう</br></br>
もし、思い出せないときはえがおの建築士に話しかけて`||agent.【ヒント】||`ボタンを押してからCキーを押してみましょう</br>