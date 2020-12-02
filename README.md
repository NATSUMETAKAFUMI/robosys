ロボットシステム学の演習で作ったデバイスドライバ

実装内容
こちらは、講義内で作成したデバイスドライバに変更を加え作成しています。
・0を入力したら青色LEDが点灯して赤色LEDは消灯する。
・1を入力したら赤色LEDが点灯して青色LEDは消灯する。

用意する物
・Raspberry Pi 4 ModelB
・ブレッドボード
・LED *2
・抵抗　300Ω *2
・ジャンパー線 オス−メス *4

回路
以下のように回路を組みました。



LEDはそれぞれのアノードがGPIO25,GPIO16に接続しています。GNDはどこでも構いません。

ビルド
実行する場合、以下のように行ってください。

$ git clone https://github.com/NATSUMETAKAFUMI/robosys.git  
$ cd robosys/myled  
$ make  
$ sudo insmod myled.ko  
$ sudo chmod 666 /dev/myled0  

実行した場合
0を入力した場合
$ echo 0 > /dev/myled0  

 青色LEDが点灯して赤色LEDは消灯します。

１を入力した場合
$ echo 1 > /dev/myled0

赤色LEDが点灯して青色LEDは消灯します。

実行動画


youtubeにあげた実行動画はこちらになります。

https://youtu.be/cwWkn6vTT5g
