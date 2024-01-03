# mypkg
![test](https://github.com/riki-ogata/mypkg/actions/workflows/test.yml/badge.svg)

* このリポジトリは, ROS2のパッケージである.
* talkerが数字をカウントアップし，それをトピックを通してInt16型のメッセージを送信し，listenerが受け取って表示させる
## 各ノードとトピック 
* ノードを機能させるためにはターミナルが2つ必要．
* talkerはcountupというトピックを通して Int16型のメッセージを送信する．
* listenerはcountupからInt16型のメッセージを受信して出力する．

## 実行例
例では端末1をtalker側，端末2をlistener側とし, 先にtalkerを実行する．
* 端末1 (入力)
```
$ ros2 run mypkg talker
```

* 端末2 (入力)
```
$ rou2 run mypkg listener
```
出力結果は以下のようになる．

* 端末2 (出力)
```
[INFO] [1704260191.602810331] [listener]: Listen: 0
[INFO] [1704260192.085857482] [listener]: Listen: 1
[INFO] [1704260192.585727688] [listener]: Listen: 2
[INFO] [1704260193.085719964] [listener]: Listen: 3
[INFO] [1704260193.586003592] [listener]: Listen: 4
[INFO] [1704260194.085678061] [listener]: Listen: 5
[INFO] [1704260194.585566690] [listener]: Listen: 6
[INFO] [1704260195.085947373] [listener]: Listen: 7
[INFO] [1704260195.585690720] [listener]: Listen: 8
[INFO] [1704260196.085720965] [listener]: Listen: 9
[INFO] [1704260196.585565102] [listener]: Listen: 10
(以下略)
```

# launchファイル
* launchファイル内のtalk_listen.launch.pyを実行することで複数のノードを同時に立ち上げることが可能である.
## 実行例

```
$ ros2 launch mypkg talk_listen.launch.py
[INFO] [launch]: All log files can be found below /home/f17026/.ros/log/2024-01-03-14-40-05-838451-DESKTOP-UQLQL6C-5816
[INFO] [launch]: Default logging verbosity is set to INFO
[INFO] [talker-1]: process started with pid [5818]
[INFO] [listener-2]: process started with pid [5820]
[listener-2] [INFO] [1704260406.829968713] [listener]: Listen: 0
[listener-2] [INFO] [1704260407.313930342] [listener]: Listen: 1
[listener-2] [INFO] [1704260407.814054563] [listener]: Listen: 2
[listener-2] [INFO] [1704260408.314757447] [listener]: Listen: 3
[listener-2] [INFO] [1704260408.814661697] [listener]: Listen: 4
[listener-2] [INFO] [1704260409.314510602] [listener]: Listen: 5
[listener-2] [INFO] [1704260409.814520259] [listener]: Listen: 6
[listener-2] [INFO] [1704260410.314647376] [listener]: Listen: 7
[listener-2] [INFO] [1704260410.814620113] [listener]: Listen: 8
[listener-2] [INFO] [1704260411.314651170] [listener]: Listen: 9
[listener-2] [INFO] [1704260411.814841776] [listener]: Listen: 10
(以下略)
```

## 必要なソフトウェア
* python
* Ubuntu20.04
  * ROS2 humble

## テスト環境
* Ubuntu22.04(container:ryuichiueda/ubuntu22.04-ros2:latest)

## 著作権・ライセンス
* このソフトウェアパッケージは，[3条項BSDライセンス](https://opensource.org/license/bsd-3-clause/)の下，再頒布および使用が許可されます．
* このパッケージのコードは，上田隆一先生の[スライド](https://github.com/ryuichiueda/my_slides/tree/master/robosys_2022)（CC-BY-SA 4.0 by Ryuichi Ueda）のものを，本人の許可を得て自身の著作としたものです．
* © 2023 Riki Ogata
