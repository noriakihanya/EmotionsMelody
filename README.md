# EmotionsMelody
***- Your words will be music. -***

日本語の感情分析ライブラリHuggingface Transformersを用いてあなたの歌詞を分析し、歌詞の感情に適したコード進行を提示する。提示されたコード進行に基づいて音楽生成ライブラリMagentaで自動で音楽を生成する。

# DEMO
「詩をコードに変換」セルの" text_to_chord("key","lyric") "に以下のように入力することで、コード進行が出力される。

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

「Magentaでメロディを生成」「生成音楽の再生」を実行することで、生成された音楽を確認することができる。
<img width="583" alt="スクリーンショット 2022-05-17 14 01 40" src="https://user-images.githubusercontent.com/105255463/168732872-b32556e3-0a57-4ad8-aa47-e4392ffdea2a.png">

生成された音楽は以下のようになっている。
<img width="1007" alt="スクリーンショット 2022-05-17 14 05 11" src="https://user-images.githubusercontent.com/105255463/168733178-60228405-42bb-4e3e-b14c-9646b1708009.png">
※MIDIファイルが出力されるためDAWソフトなどで自由に編集することも可能

# Features

"hoge"のセールスポイントや差別化などを説明する

# Requirement

"hoge"を動かすのに必要なライブラリなどを列挙する

* huga 3.5.2
* hogehuga 1.0.2

# Installation

Requirementで列挙したライブラリなどのインストール方法を説明する

```bash
pip install huga_package
```

# Usage

DEMOの実行方法など、"hoge"の基本的な使い方を説明する

```bash
git clone https://github.com/hoge/~
cd examples
python demo.py
```

# Note

注意点などがあれば書く

# Author

作成情報を列挙する

* 作成者
* 所属
* E-mail

