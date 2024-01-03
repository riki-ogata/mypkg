# mypkg
![test](https://github.com/riki-ogata/mypkg2/actions/workflows/test.yml/badge.svg)
* このリポジトリは, ROS2のパッケージである.
* talkerが数字をカウントアップし，それをトピックを通してInt16型のメッセージを送信し，listenerが受け取って表示させる
## 各ノードとトピック 
* ノードを機能させるためにはターミナルが2つ必要．
* talkerはcountupというトピックを通して Int16型のメッセージを送信する．
* listenerはcountupからInt16型のメッセージを受信して出力する．

## 実行例
例では端末1をtalker側，端末2をlistener側として実行する．
* 端末1 (入力)
```
$ ros2 run mypkg talker
```

* 端末2 (入力)
```
$ rou2 run mypkg listener
```

## launchファイル


## 必要なソフトウェア
* python
* Ubuntu20.04
  * ROS2 humble

## テスト環境
* Ubuntu22.04

## 著作権・ライセンス
* このソフトウェアパッケージは，[3条項BSDライセンス](https://opensource.org/license/bsd-3-clause/)の下，再頒布および使用が許可されます．
* このパッケージのコードは，上田隆一先生の[スライド](https://github.com/ryuichiueda/my_slides/tree/master/robosys_2022)（CC-BY-SA 4.0 by Ryuichi Ueda）のものを，本人の許可を得て自身の著作としたものです．
* © 2023 Riki Ogata
