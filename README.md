# EmotionsMelody
***- あなたの言葉が音楽になる -***

日本語の感情分析ライブラリHuggingface Transformersを用いて歌詞を分析し、歌詞の感情に適したコード進行を提示する。提示されたコード進行に基づいて音楽生成ライブラリMagentaで自動で音楽を生成する。

# DEMO
●「詩をコードに変換」セルの`text_to_chord("key","lyric") `に`key`と`lyric`を入力することで、コード進行が出力される。

```
#ボブ・ディラン　風に吹かれて
text_to_chord("D","la3")
text_to_chord("D","人は何度見上げれば空が見えるのか")
text_to_chord("D","人にはいくつ耳があれば人々の悲しみが聞こえるのか")
text_to_chord("D","どれ位の人が死んだら")
text_to_chord("D","あまりにも多くの人が亡くなったことに気づくのか")
text_to_chord("D","友よ答えは風に吹かれて")
text_to_chord("D","風に吹かれている")
text_to_chord("D","la3")
```

```
la3 : G F# Bm
人は何度見上げれば空が見えるのか : Emaj7 Em7 Emaj7 Em7
人にはいくつ耳があれば人々の悲しみが聞こえるのか : G F#7 Bm Am D
どれ位の人が死んだら : Dmaj7 A/C# Bm Dm
あまりにも多くの人が亡くなったことに気づくのか : G A D G A D
友よ答えは風に吹かれて : G#/C A#m G# G#/C A#m G#
風に吹かれている : Bm F#/Bb Bm F#/Bb
la3 : G F# Bm
```

●「Magentaでメロディを生成」の実行で、音楽を生成

●「生成音楽の再生」の実行で、生成された音楽を確認

<img width="583" alt="スクリーンショット 2022-05-17 14 01 40" src="https://user-images.githubusercontent.com/105255463/168732872-b32556e3-0a57-4ad8-aa47-e4392ffdea2a.png">

生成された音楽ファイルの中身は以下のようになっている。
<img width="1007" alt="スクリーンショット 2022-05-17 14 05 11" src="https://user-images.githubusercontent.com/105255463/168733178-60228405-42bb-4e3e-b14c-9646b1708009.png">
※MIDIファイルが出力されるためDAWソフトなどで自由に編集することも可能

# Features

・JーPOPのコード進行を学習したAIがデータベースから歌詞に適したコード進行を提示するため、音楽の知識がなくても作曲が可能

・音楽学習生成ライブラリMagentaで学習させたモデルを用いているため、別途自分で学習させたモデルを使用することで自分好みの音楽を生成させることが可能

・複数のMIDIファイルを結合させているため、Magentaよりも複雑な音楽を生成することが可能

・生成された音楽はMIDIファイルとして取得することができるため、最終的に自分で自由に編集が可能

# Requirement

* Magenta
* Transformers
* その他

# Installation

パッケージのインストール

```
!git clone https://github.com/noriakihanya/EmotionsMelody.git
!pip install -r /content/EmotionsMelody/requirements.txt
!apt install fluidsynth
!cp /usr/share/sounds/sf2/FluidR3_GM.sf2 ./font.sf2
!pip install midi2audio
```

# Usage

Google Colaboratoryを使用する場合、基本的にセルを上から順番に実行することができるため「詩をコードに変換」セルの使い方について以下で説明

「詩をコードに変換」セルの`text_to_chord("key","lyric")`にそれぞれ以下のように入力する。

　・keyはC G D A E B F# C# F Bb Eb Ab Db Gb Cb　から選択

　・lyrci:"la+n"を入力することで、n個分のコード進行がランダムで表示される。現在１〜１０まで対応（９は対象なし）
　　なお、n個分のコード進行が得られないことがあるため、任意のコード進行が得られるまで実行ボタンを押下してください。

　以下のように入力するとコード３つ分のコード進行が出力される（が、コードが１つや２つの時もあるため何度か実行ボタンを押して任意のコード数を出力させる）。※対応方法については検討中

```
text_to_chord("D","la3")
```
```
la3 : G F# Bm
```

　・歌詞を増やす場合、text_to_chord("key","lyric")をコピーし、任意の箇所にペーストすることで好きな場所に音楽を生成させることができる。

# Issue

今後の課題

・今回使用しているモデルには学習データを多く使用できなかったため、生成される音楽が似通ってしまった。

・感情分析をしているにもかかわらず、感情に沿ったメロディが生成されているとは言い難い。

上記に対応するために今後の取り組みとして、より多くの音楽を学習させ、学習させる音楽を緻密に分類し同じような曲調を集めて学習させることで、より歌詞の内容に沿った音楽が生成されるように工夫したい。

# Author

* Noriaki HANYA
* E-mail

