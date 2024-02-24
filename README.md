※日本語の説明は英語の下にあります。

# description
This library is to control LSM9DS1 sensor for m5 series, UI FLOW and micropython.

I reffer https://github.com/hoihu/projects/blob/master/raspi-hat/lsm9ds1.py to make this code.
I'd like to say thank you for https://github.com/hoihu to make such great work.

## why I made it
I like m5 series and UI FLOW, but I cannot find any sample to use LSM9DS1 for m5 and UI FLOW.
Then I decided to port it.

## how to use

### for micropython
1. open micropython editor
2. copy "lsm9ds1_m5.py" and paste it to micropython editor
3. add code below
```
i2c0 = i2c_bus.easyI2C(i2c_bus.PORTA, 0x00, freq=400000)
lsm = LSM9DS1(i2c0, address_gyro=0x6A,  address_magnet=0x1C)
while True:
  x,y,z = lsm.read_accel()
#  x,y,z = lsm.read_gyro()
#  x,y,z = lsm.read_magnet()
  print("{},{},{}".format(x,y,z))
  wait_ms(100)
```

### for UI FLOW
1. reffer the image below

![image](https://github.com/matsuura-h/lsm9ds1_micropython/assets/27671298/6294f89a-a20c-4e09-b1e3-c8dac1a8957f)

![image](https://github.com/matsuura-h/lsm9ds1_micropython/assets/27671298/96200949-e47e-40dd-9dd0-d14f0149631f)

--日本語---------------------------------------

# 説明
LSM9DS1をm5系、UI FLOWやmicropythonで使うためのライブラリです。

https://github.com/hoihu/projects/blob/master/raspi-hat/lsm9ds1.pyを参考にしています。
素晴らしいライブラリを作ってくださったhttps://github.com/hoihuさんに感謝。

## なぜこれを作ったのか？
m5やUI FLOW、micropythonを気に入って使っているのですが、LSM9DS1の作例がArduino C++やcircuitpythonしかなく、m5でサクッと使えるものがなかったので自分で移植してみました。
easyI2CやLSM9DS1の参考文献がほとんど無く苦労しました。

## 使い方

### micropython向け
1. UI FLOWのmicropythonのエディタを開く
2. "lsm9ds1_m5.py"を開いて、micropythonのエディタの適当な場所にコピペする
3. 以下のコードを追加すれば、動きます（当然、別の方法でimportしても動きます）
```
i2c0 = i2c_bus.easyI2C(i2c_bus.PORTA, 0x00, freq=400000)
lsm = LSM9DS1(i2c0, address_gyro=0x6A,  address_magnet=0x1C)
while True:
  x,y,z = lsm.read_accel()
#  x,y,z = lsm.read_gyro()
#  x,y,z = lsm.read_magnet()
  print("{},{},{}".format(x,y,z))
  wait_ms(100)
```

### UI FLOW向け
1. 画像を見てください


# license
This software is released under the MIT License
MITライセンスを適用します。
https://opensource.org/license/mit
