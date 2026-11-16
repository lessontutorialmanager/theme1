# LESSON1 原木をこわそう
```block
player.onChat("run", function () {
    agent.teleport(world(-19, 1, -21), SOUTH)
    for (let index = 0; index < 12; index++) {
        if (agent.inspect(AgentInspection.Block, FORWARD) == LOG_OAK) {
            agent.destroy(FORWARD)
            agent.move(FORWARD, 1)
        } else {
            agent.move(FORWARD, 1)
        }
    }
})
```

```template
player.onChat("run", function () {
	
})
```

## 0.条件分岐を使って原木をこわそう @unplugged
条件分岐でエージェントを動かしてじゃまな原木をこわそう！<br>
<img style="display: block; margin: auto;" height="50%" width="90%" src="https://i.ibb.co/TcjJGSN/l5-kowasu-betukakudo.gif">

## 目標
まずはこれから作るものの形をかくにんしよう！<br>
・チャットで「run」と入力したら、エージェントに原木をこわすようにプログラミングをする<br>
・エージェントは初めにワールド-19 1 -21、南(zのプラス方向)にテレポートする<br>
・エージェントの前に原木があればこわしてからすすみ、ないときはすすむだけとする<br>
<img style="width:100%" src="https://i.ibb.co/TcjJGSN/l5-kowasu-betukakudo.gif"><br>

## 条件分岐（じょうけんぶんき）を使ってプログラミングをしよう
条件分岐（じょうけんぶんき）のプログラムは次の順に動いています<br>
⓵エージェントの前に原木があるかどうか、かくにんさせる<br>
⓶【もし…なら…】の中は条件（じょうけん）が`||player.正しい||`ときに動く<br>
⓷【…でなければ…】の中は条件（じょうけん）が`||agent.正しくない||`ときに動く<br>
<img style="width:100%" src="https://i.ibb.co/RNM2339/l5-q1-all.gif"><br>

## エージェントに前に何のブロックがあるか、かくにんさせよう
まずは⓵の『エージェントの前に原木があるかどうか、かくにんさせる』プログラムから作ります<br>
<img style="width:100%" src="https://i.ibb.co/0cs1NQM/bunki1.png"><br>

## エージェントに前に何のブロックがあるか、かくにんさせよう
エージェントにブロックがあるかかくにんさせるには<br>
【エージェントの前のブロック】<img style="width:90%" src="https://i.ibb.co/xh5Qpbw/burokku.png">と【ブロック】<img style="width:20%" src="https://i.ibb.co/64pFdzQ/block.png">を使います
どのように使うか、次にページからプログラムを作ってみましょう<br>


## 1.条件分岐を追加してみましょう

`||logic.論理（ろんり）||`ボタンをクリックしてその中の`||logic.もし真なら…でなければ…||`と書いてあるブロックを`||player.チャットコマンド～||`の中にドラッグしてみましょう<br>
さらに`||logic.論理||`ボタンをクリックしてその中の`||logic.0=0||`と書いてあるブロックを`||logic.真||`に重ねましょう<br>
<img style="width:100%" src="https://i.ibb.co/fdthWrQ/l5q1-4.gif"></P>
```block
player.onChat("run", function () {
    if (0 == 0) {
    	
    } else {
    	
    }
})

```

## 2.エージェントに原木が前にあるかかくにんさせましょう

`||agent.エージェント||`ボタンをクリックしてその中の`||agent.エージェントの前のブロック||`と書いてあるブロックを`||logic.0=0||`の左の0に重ねてみましょう<br>
さらに`||blocks.ブロック||`ボタンをクリックしてその中の<img style="width:20%" src="https://i.ibb.co/64pFdzQ/block.png">を`||logic.0=0||`の右の0に重ねてみましょう<br>
そして<img style="width:20%" src="https://i.ibb.co/64pFdzQ/block.png">`||blocks.草ブロック▼||`をクリックして<img style="width:20%" src="https://i.ibb.co/vwMhYMp/pg1block.png">`||blocks.オークの原木||`にしましょう<br>
<img style="width:100%" src="https://i.ibb.co/TmmFgkv/l5q1-5.gif"><br>
```block
player.onChat("run", function () {
    if (agent.inspect(AgentInspection.Block, FORWARD) == LOG_OAK) {
    	
    } else {
    	
    }
})

```

## エージェントに前にあるブロックをこわしてもらおう
これで条件分岐を使うプログラムの用意ができました<br>
次に⓶の『【もし…なら…】の中にはその条件（じょうけん）が`||player.正しい||`ときに動く』プログラムを作ります<br>
<img style="width:100%" src="https://i.ibb.co/H7kYT1y/bunki2pg.png"><br>
エージェントの動きは</br>【原木があるとき】</br>１.原木をこわす</br>２.前にすすませる</br>となります<br>
<img style="width:100%" src="https://i.ibb.co/ZLzbG2V/l5-aru-kowasu-genboku.gif"><br>

## 3.原木が前にあったときにエージェントにこわしてもらいましょう

`||agent.エージェント||`ボタンをクリックしてその中の`||agent.エージェントに前を破壊（はかい）させる||`と書いてあるブロックを`||logic.もし…なら||`の中にドラッグしてみましょう<br>
さらに`||agent.エージェント||`ボタンをクリックしてその中の`||agent.エージェントを前に１ブロック移動（いどう）させる||`と書いてあるブロックを`||agent.エージェントに前を破壊させる||`の下にドラッグしてみましょう<br>
<img style="width:100%" src="https://i.ibb.co/Hgmd2S0/l5q1-7.gif"><br>
```block
player.onChat("run", function () {
    if (agent.inspect(AgentInspection.Block, FORWARD) == LOG_OAK) {
        agent.destroy(FORWARD)
        agent.move(FORWARD, 1)
    } else {
    	
    }
})

```

## エージェントを前にすすませよう
次に⓷の『【…でなければ…】の中にはその条件（じょうけん）が`||agent.正しくない||`ときに動く』プログラムを作ります<br>
<img style="width:100%" src="https://i.ibb.co/7QKyvZB/bunki3.png"><br>
エージェントの動きは</br>【原木がないとき】</br>１.前にすすませる</br>となります<br>
<img style="width:100%" src="https://i.ibb.co/jVfq7Rz/l5-nai-susumu-genboku.gif"><br>

## 4.原木が前にないときにエージェントを移動させましょう

`||agent.エージェント||`ボタンをクリックしてその中の`||agent.エージェントを前に１ブロック移動させる||`と書いてあるブロックを`||logic.…でなければ…||`の中にドラッグしてみましょう<br>
<img style="width:100%" src="https://i.ibb.co/kqBrSmt/l5q1-9.gif"><br>
```block
player.onChat("run", function () {
    if (agent.inspect(AgentInspection.Block, FORWARD) == LOG_OAK) {
        agent.destroy(FORWARD)
        agent.move(FORWARD, 1)
    } else {
        agent.move(FORWARD, 1)
    }
})

```
## くりかえし処理を使おう
条件分岐を使って原木が前にあるときとないときの動きが作れました<br>
この動きを必要（ひつよう）な数だけくりかえしましょう<br>
原木をすべてこわすにはエージェントに何回くりかえさせればいいでしょうか？<br>
<img style="width: 50%; display: inline-block;" src="https://i.ibb.co/ZLzbG2V/l5-aru-kowasu-genboku.gif"><img style="width: 50%; display: inline-block;" src="https://i.ibb.co/jVfq7Rz/l5-nai-susumu-genboku.gif"><br>
<img style="display: block; margin: 0 auto; width: 25%;" src="https://i.ibb.co/SKKzwsC/sita.png"><br>
<img style="width:100%" src="https://i.ibb.co/RNM2339/l5-q1-all.gif"><br>

## くりかえし処理を使おう
さいしょの原木からさいごの原木までは『１２ブロック』でした<br>
いままで作ったプログラムを原木をすべてこわすために１２回くりかえしましょう<br>
<img style="width:100%" src="https://i.ibb.co/BqQqs5K/l5loop.png"><br>

## 5.ループを追加してみましょう

`||loops.ループ||`ボタンをクリックしてその中の`||loops.くりかえし４回||`と書いてあるブロックで今までに作ったプログラムをはさみましょう<br>
`||math.４回||`の数字をクリックして`||math.１２回||`に変えましょう<br>
<img style="width:100%" src="https://i.ibb.co/pzjpKC4/l5q1-11.gif">
```block
player.onChat("run", function () {
    for (let index = 0; index < 12; index++) {
        if (agent.inspect(AgentInspection.Block, FORWARD) == LOG_OAK) {
            agent.destroy(FORWARD)
            agent.move(FORWARD, 1)
        } else {
            agent.move(FORWARD, 1)
        }
    }
})

```

## エージェントを原木をこわしはじめる場所にテレポート
さいごにエージェントを原木をこわしはじめる場所にテレポートさせましょう<br>

## 6.エージェントをテレポートさせよう

`||agent.エージェント||`ボタンをクリックしてその中の`||agent.エージェントを…へ西(xのマイナス方向)向きにテレポートさせる||`と書いてあるブロックを`||loops.くりかえし１２回||`の上にドラッグしてみましょう<br>
`||agent.西(xのマイナス方向)▼||`をクリックして`||agent.南(zのプラス方向)▼||`に変えましょう<br>
<img style="width:100%" src="https://i.ibb.co/sqk02D9/l5q1-13.gif"><br>
```block
player.onChat("run", function () {
    agent.teleport(pos(0, 0, 0), SOUTH)
    for (let index = 0; index < 12; index++) {
        if (agent.inspect(AgentInspection.Block, FORWARD) == LOG_OAK) {
            agent.destroy(FORWARD)
            agent.move(FORWARD, 1)
        } else {
            agent.move(FORWARD, 1)
        }
    }
})

```

## 7.座標を変更してみましょう

`||positions.ポジション||`ボタンをクリックしてその中の`||positions.ワールド0 0 0||`を`||agent.~0~0~0||`の上までドラッグします<br>
`||positions.ワールド0 0 0||`を`||positions.ワールド-19 1 -21||`に変えましょう<br>
<img style="width:100%" src="https://i.ibb.co/qkszc9M/l5q1-14.gif"><br>
```block
player.onChat("run", function () {
    agent.teleport(world(-19, 1, -21), SOUTH)
    for (let index = 0; index < 12; index++) {
        if (agent.inspect(AgentInspection.Block, FORWARD) == LOG_OAK) {
            agent.destroy(FORWARD)
            agent.move(FORWARD, 1)
        } else {
            agent.move(FORWARD, 1)
        }
    }
})

```

## 8.『実行』ボタンをクリックしましょう
画面右下にある緑の『▶』ボタンをクリックして作ったプログラムを実行し、チャットコマンドで`||player.run||`と入力してみましょう