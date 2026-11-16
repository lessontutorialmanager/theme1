# LESSON3 畜舎を直そう
```block
player.onChat("run", function () {
    agent.teleport(world(-13, 1, -24), SOUTH)
    for (let index = 0; index < 13; index++) {
        if (agent.inspect(AgentInspection.Block, FORWARD) == WARPED_FENCE) {
            agent.move(RIGHT, 1)
        } else {
            agent.setItem(WARPED_FENCE, 1, 1)
            agent.place(FORWARD)
            agent.move(RIGHT, 1)
        }
    }
})
```

```template
player.onChat("run", function () {
    agent.teleport(world(-19, 1, -21), SOUTH)
    for (let index = 0; index < 13; index++) {
        if (agent.inspect(AgentInspection.Block, DOWN) == SAND) {
            agent.setItem(GRASS, 1, 1)
            agent.destroy(DOWN)
            agent.place(DOWN)
            agent.move(FORWARD, 1)
        } else {
            agent.move(FORWARD, 1)
        }
    }
})
```


## 目標
先ほど作ったプログラムを改造（かいぞう）して、フェンスをおかせよう！<br>
・チャットで「run」と入力したら、エージェントにフェンスをおくようにプログラミングをする<br>
・エージェントははじめにワールド-13 1 -24、南(zのプラス方向)にテレポートする<br>
・エージェントの前にフェンスがあれば右にすすむだけ、ないときはフェンスをおいて右にすすむようにする<br>
<img style="width:100%" src="https://i.ibb.co/0Qw8dtj/fensu.gif"><br>

## 今まで作ったプログラムを使って、プログラムを作ろう
今までは【前（下）にブロックがあれば、こわしたりおいたりする・なければ、すすむだけ】というプログラムを作りました<br>
ここでは`||player.【前（下）にブロックがあればすすむだけ・なければ、おく】||`というプログラムにしましょう<br>
<img style="width:100%" src="https://i.ibb.co/tZBczVR/image.png"><br>

## プログラムの作りをかんがえよう
今回のプログラムのエージェントの動きは次のようにします<br>
１.エージェントの前にフェンスがあるか、かくにんさせる<br>
２.【フェンスがあるとき】</br>・右にすすませる<br>
３.【フェンスがないとき】</br>・フェンスをおく➡右にすすませる<br>
<img style="width:100%" src="https://i.ibb.co/HFDrnqw/l5-q3-all.gif"><br>

## 1.いらないプログラムを消そう

`||agent.エージェントの下を破壊（はかい）させる||`と書いてあるブロックにカーソルを合わせて右クリックをしましょう<br>
<img style="width:90%" src="https://i.ibb.co/ys9XXRF/l2deletemozi.png">をクリックするといらないブロックを消すことができます<br>

## 2.プログラムを入れかえましょう

`||logic.もし…||`の中のプログラムと、`||logic.でなければ…||`の中のプログラムをいれかえましょう<br>
`||logic.でなければ…||`の中の`||agent.エージェントを前に１ブロック移動させる||`と書いてあるブロックを`||agent.エージェントに…を１個…設定させる||`の上にドラッグしましょう</br>
<img style="width:100%" src="https://i.ibb.co/4SwnxGG/l5-q3-3.gif"><br>

## 3.プログラムを入れかえましょう

`||logic.もし…||`の中の`||agent.エージェントに…を１個…設定させる||`と書いてあるブロックをドラッグすると、そのプログラムから下も付いてきます<br>
そのプログラムたちを`||logic.でなければ…||`の中にドラッグしましょう<br>
<img style="width:100%" src="https://i.ibb.co/BjvdML5/l5-q3-4.gif"><br>

## フェンスが前にあるとき、ないときのそれぞれのプログラム

エージェントの前にフェンスが`||loops.ある||`ときは、なにもせずに右に１ブロック動かしましょう<br>
<img style="width:100%" src="https://i.ibb.co/SRDZwRC/l5-aru-susumu-fensu.gif"><br>
エージェントの前にフェンスが`||loops.ない||`ときは、フェンスをおいて、右に１ブロック動かしましょう<br>
<img style="width:100%" src="https://i.ibb.co/MsvJHTv/l5-nai-oku-fensu.gif"><br>

## 5.フェンスがあるときのエージェントのプログラム

まずはフェンスが前にあるときのプログラムを作ります<br>
`||logic.もし…||`の中の`||agent.エージェントを前に１ブロック移動させる||`と書いてあるブロックの`||agent.前▼||`をクリックして、`||agent.右▼||`にしましょう<br>

## 6.フェンスがないときのエージェントのプログラム

次にフェンスが前にないときのプログラムを作ります<br>
`||logic.でなければ…||`の中の<img style="width:20%" src="https://i.ibb.co/64pFdzQ/block.png">草ブロックをクリックして<img style="width:20%" src="https://i.ibb.co/nr7R4rK/fence.png">歪（ゆが）んだフェンスにしましょう<br>
そして`||logic.でなければ…||`の中の`||agent.エージェントに下へ置かせる||`の`||agent.下▼||`をクリックして、`||agent.前▼||`にしましょう<br>
さいごに`||logic.でなければ…||`の中の`||agent.エージェントを前に１ブロック移動させる||`と書いてあるブロックの`||agent.前▼||`をクリックして、`||agent.右▼||`にしましょう<br>

## プログラムをととのえよう
これでエージェントの動きはできました<br>
次に条件分岐（じょうけんぶんき）の条件（じょうけん）、くりかえしの数、エージェントのスタート地点を入力していきましょう<br>
<img style="width:100%" src="https://i.ibb.co/rffxZ1Z/last.png"><br>

## 7.条件分岐（じょうけんぶんき）の条件（じょうけん）をかえてみましょう

フェンスはエージェントの前にあるので、エージェントにかくにんしてもらう場所を【下】から【前】にします<br>
<img style="width:90%" src="https://i.ibb.co/Dz5zb3X/if2.png">の`||agent.下▼||`をクリックして、`||agent.前▼||`にしましょう<br>
<img style="width:20%" src="https://i.ibb.co/rHmHfky/pg2block.png">砂ブロックをクリックして<img style="width:20%" src="https://i.ibb.co/nr7R4rK/fence.png">歪（ゆが）んだフェンスにしましょう<br>

## 8.くりかえしの数をかえましょう

さいしょのフェンスの場所からさいごの場所までは『１３ブロック』でした<br>
くりかえしの数はそのまま１３回にしておきましょう<br>
<img style="width:100%" src="https://i.ibb.co/7vFCttz/l5loop2.png"><br>

## 9.エージェントをテレポートさせよう

`||positions.ワールド-19 1 -21||`を`||positions.ワールド-13 1 -24||`に変えましょう<br>

## 10.『実行』ボタンをクリックしましょう
画面右下にある緑の『▶』ボタンをクリックして作ったプログラムを実行し、チャットコマンドで`||player.run||`と入力してみましょう