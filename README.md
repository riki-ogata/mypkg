# mypkg
![test](https://github.com/riki-ogata/mypkg2/actions/workflows/test.yml/badge.svg)

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
[INFO] [launch]: All log files can be found below /home/sakumahinata/.ros/log/2023-12-27-03-10-54-671057-DESKTOP-6Q66L93-631
[INFO] [launch]: Default logging verbosity is set to INFO
[INFO] [talker-1]: process started with pid [633]
[INFO] [listener-2]: process started with pid [635]
[listener-2] [INFO] [1703614255.578763603] [listener]: Listen: 0
[listener-2] [INFO] [1703614256.069406272] [listener]: Listen: 1
[listener-2] [INFO] [1703614256.570036498] [listener]: Listen: 2
[listener-2] [INFO] [1703614257.069966051] [listener]: Listen: 3
[listener-2] [INFO] [1703614257.569943873] [listener]: Listen: 4
[listener-2] [INFO] [1703614258.068709380] [listener]: Listen: 5
(以下略)
```

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
