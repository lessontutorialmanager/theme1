```template
player.onChat("run1", function () {
    blocks.fill(
    PLANKS_BIRCH,
    world(23, 72, 117),
    world(30, 77, 125),
    FillOperation.Hollow
    )
    blocks.place(OAK_DOOR, world(23, 73, 121))
    blocks.fill(
    GLASS,
    world(25, 74, 117),
    world(28, 75, 117),
    FillOperation.Replace
    )
})
player.onChat("run2", function () {
    blocks.fill(
    BRICKS,
    world(26, 72, 125),
    world(30, 76, 131),
    FillOperation.Hollow
    )
    blocks.fill(
    GLASS,
    world(26, 74, 127),
    world(26, 75, 129),
    FillOperation.Replace
    )
    blocks.fill(
    AIR,
    world(27, 73, 125),
    world(29, 75, 125),
    FillOperation.Replace
    )
})
player.onChat("run3", function () {
    blocks.fill(
    STONE_BRICKS,
    world(24, 74, 134),
    world(30, 79, 140),
    FillOperation.Hollow
    )
    blocks.place(SPRUCE_DOOR, world(24, 75, 137))
    blocks.fill(
    GLASS,
    world(26, 79, 136),
    world(28, 79, 138),
    FillOperation.Replace
    )
})
```

# 学んだプログラムを使ってみよう

## プログラムを自由にくみかえよう
今日、学んだプログラムを見てみましょう<br>
見終わったら`||完了||`をクリックしてすべての使って自由にプログラミングをしてみましょう<br>
<img style="width:100%" src="https://i.ibb.co/Sf6zB2y/finishok.gif"><br>