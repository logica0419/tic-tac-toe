# tic-tac-toe

Go が好きなので、Go で CLI の 〇✕ ゲームを作りました (ただの変態)。  
外部パッケージを使わず、標準パッケージのみでの実装です。

## インストール方法

下のうちお好きな方法で遊んでください。

### 直接ダウンロード

[Releases](https://github.com/logica0419/tic-tac-toe/releases) から直で DL・解凍・実行してください。

### Go を使ってインストール

前提: go

```sh
go install github.com/logica0419/tic-tac-toe@latest
```

してください。`tic-tac-toe`コマンドでいつでも遊べます。  
コマンドが見つからない場合、`$GOBIN`が`$PATH`に追加されているか確認してください。

### リポジトリをクローンする

環境を汚したくない人向け。

前提: go & git  
適当なディレクトリで

```sh
git clone https://github.com/logica0419/tic-tac-toe
cd tic-tac-toe
go run *.go
```

してください。  

## 遊び方

実行すると案内が出るので、それに従ってやれば大丈夫です。楽しんで。

## 敵 AI の裏話

難易度設定とそれぞれのアルゴリズムのお話です。
もっと強くするアイデア等あればご一報ください。

- Easy
  - 選べるセルの中から完全ランダムで選ぶ
- Normal
  - そのターンで勝てる手が存在する (2つ並びがある) 時、勝てる手を出す
  - 無ければ優先して真ん中を取りに行く、埋まっていたらランダム
- Hard
  - そのターンで勝てる手が存在する (✕のリーチがある) 時、勝てる手を出す
  - 勝てる手がなく、次のターンで負けそうな (○のリーチがある) 時、それを阻止する手を出す
  - 勝てる手・負けを阻止する手が無い場合、リーチができる組み合わせを優先して取る
  - それも無ければ優先して真ん中を取りに行く、埋まっていたらランダム
