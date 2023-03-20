# 【Pytorch】 Seq2Seqによる時系列予測

「【Pytorch】 Seq2Seqによる時系列予測」（https://qiita.com/apple-pie/items/e018900c5713934312c3 ）に使用したコードです。
seq2seq.ipynbをダウンロードしてgoogle colabなどで実行するのみで予測を行うことができます。

## 概要
自然言語処理や音声処理でよく用いられる時系列予測に応用しました。モデルの概略図は以下のようになります。

<img width="800" src="https://user-images.githubusercontent.com/87755637/223008686-a8b9124e-fbb2-4eec-a864-56c460dc3da6.png">

seabornの中にあるair passengersというデータを用いて、このSeq2Seqによる予測を行いました。
訓練用、評価用、テスト用データを以下のように分け、訓練用データで訓練し、評価用データで最も良いで精度を達成したモデルを最も良いモデルとして、テスト用データの予測を行いました。

<img width="400" src="https://user-images.githubusercontent.com/87755637/223009329-44b296c9-5d92-4969-9755-3e1f5bb8bf9c.png">

結果は季節変動は捉えられているが、傾向変動が捉えられませんでした。

<img width="400" src="https://user-images.githubusercontent.com/87755637/223009154-135985f7-9c04-4a7a-b60b-83e35fb6bb67.png">

パラメータなどを調整したりすれば改善するかもしれません。
時間のある方は試してみてください。

# 追記
### 3/16
データをStandardScaleするのを忘れていました。StandardScaleした後の結果が以下になります。
<img width="400" src="https://user-images.githubusercontent.com/87755637/225816600-6b043b25-bdd8-46af-997e-3a17b918029c.png">

大分変わりましたね。元のデータサイズにしたければ、これをInverse Transformすれば大丈夫です。

### 3/17
訓練、評価用コードのところを少し改良しました
