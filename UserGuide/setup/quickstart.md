# クイックスタートガイド

## 概要

本ページでは、本プログラムを動作させるために最低限必要な手順を紹介します。
ここでは、Raspberry Pi上でUSBメモリにデータを保存する方法[^1]を紹介します。
## 設定

### 受信機の設定

インタラクティブモードで受信機プログラムを書き込んだTweliteの値を、次のように設定します。

|設定項目|値|
| - | - |
|ApplicationID|子機側と同じ値|
|Optionbit|0x00000020|

設定項目の詳細は、[MONOWIRELESSのホームページ](https://mono-wireless.com/jp/products/TWE-APPS/App_Tag/interactive.html#parent)をご覧ください。

設定が終わった

## USBメモリの設定

初期設定では、本プログラムはセンサから得たデータを、USBメモリ(/media/pi/*)に保存する構成となっています。
CUIをご利用の方は、USBメモリを手動でマウントする必要があります。

## Raspberry Piの設定

セットアップが完了した受信機と、USBメモリをUSBをRaspberry Piに接続し、電源を入れてください。

1. まず、gitをインストールします。

    ```sh
    sudo apt -y update
    sudo apt -y install git
    ```

2. 次に、本リポジトリをクローンします。

    ```sh
    git clone https://github.com/Tycoh/C3less-Sensor.git
    ```

3. セットアッププログラムを実行します

    ```sh
    cd C3lessSensorService
    chmod +x setup.sh
    bash setup.sh
    ```

4. 再起動します

    ```sh
    sudo reboot
    ```

5. 再起動後、センサのデータが蓄積していることを確認します。

    ```sh
    less /media/pi/*/data.csv
    ```

データが確認できない場合は、[[トラブルシューティング|troubleshooting]]をご覧ください

[^1]: 初期設定