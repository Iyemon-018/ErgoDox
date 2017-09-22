# ErgoDox

http://rymo.hateblo.jp/entry/2017/05/02/170142


## Bash on Ubuntu on Windows をインストールする。


http://qiita.com/Aruneko/items/c79810b0b015bebf30bb

## 各種ツールのインストール

1. コマンドプロンプトを起動
1. bash を入力
1. 以下のコマンドを入力   

sudo apt-get install git gcc-avr avr-libc dfu-programmer make  
cd  
git clone https://github.com/jackhumbert/qmk_firmware.git  


## キーマップデータを編集する。

Bash on Ubuntu on Windows のフォルダはいかの場所
通常はフォルダが見えないが、エクスプローラーのパス部分に入力することで表示することが可能。

C:\Users\<ユーザー名>\AppData\Local\lxss

更に以下の改装まで潜るとデフォルトのキーマップがあるのでこれを編集する。
自分はvim使ったこと無いので、VSCodeで以下のファイルをコピーして編集した。

home\\<ユーザー名>\qmk_firmware\keyboards\ergodox_ez\keymaps\default

## ビルド方法

コマンドライン（Bash）で以下を入力する。

cd ~/qmk_firmware/  
make keyboard=ergodox_ez keymap=default  
ls .build/ergodox_ez_default.hex

すると以下のファイルが作成されるのでこれを使用してファームウェアを更新する。

home\kishii\qmk_firmware\.build\ergodox_ezdefault.hex

## 問題点

１． Teensy.exe を２回実行するとUSBが認識しなくなる

解決方法：
PCを再起動する。

２． カスタマイズしたファイルでビルドできないことがあった。

解決策：
1. qmk_firmware フォルダを削除する。
1. bash を起動中であればフォルダを削除できないので終了しておく。
1. リポジトリから最新版の環境を取得する。
1. default/keymap.c を変更する。
1. ビルドする。


原因：
不明
今のところ、PCを再起動するとこの現象が発生する。


---

## 2017-09-22現在のキーマップ

https://www.massdrop.com/configurator/ergodox?referer=XNJD4M&hash=de16527c8959761cf1a39f4e192afd14

### 2017-09-07現在のキーマップ

https://www.massdrop.com/configurator/ergodox?referer=XNJD4M&hash=fa9ff064c6ec921d57e2d5aedfb2fb1a