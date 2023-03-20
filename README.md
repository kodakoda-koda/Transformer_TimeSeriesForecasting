# 【Pytorch】 Transformerを用いた時系列予測

「【Pytorch】 Transformerを用いた時系列予測」（ ）に使用したコードです。
seq2seq.ipynbをダウンロードしてgoogle colabなどで実行するのみで予測を行うことができます。

## 概要
自然言語処理や音声処理でよく用いられるTransformerを時系列予測に応用しました。モデルの概略図は以下のようになります。

<img width="800" src="https://user-images.githubusercontent.com/87755637/226383091-e5c52e17-1c3e-4ec9-8914-6c6f128c36a8.png">


seabornの中にあるair passengersというデータを用いて、このTransformerによる予測を行いました。
訓練用、評価用、テスト用データを以下のように分け、訓練用データで訓練し、評価用データで最も良いで精度を達成したモデルを最も良いモデルとして、テスト用データの予測を行いました。

<img width="400" src="https://user-images.githubusercontent.com/87755637/223009329-44b296c9-5d92-4969-9755-3e1f5bb8bf9c.png">

結果は季節変動は捉えられているが、傾向変動が捉えられませんでした。

<img width="400" src="https://user-images.githubusercontent.com/87755637/226383340-76148587-4ccb-46e5-9cf6-f442f92188d9.png">

大体は予測できていますが、細かい部分が予測できていません。パラメータなどを調整したりすれば改善するかもしれません。
時間のある方は試してみてください。

