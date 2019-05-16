# クイックスタートガイド

## 概要

本ページでは、本プログラムを動作させるために最低限必要な手順を紹介します。
ここでは、Raspberry Pi上でUSBメモリにデータを保存する方法[^1]を紹介します。

## 設定

### MONOSTICKの設定

インタラクティブモードでMONOSTICKの値を次のように設定します。

|設定項目|値|
| - | - |
|ApplicationID|子機側と同じ値|
|Optionbit|0x00000020|

設定項目の詳細は、[MONOWIRELESSのホームページ](https://mono-wireless.com/jp/products/TWE-APPS/App_Tag/interactive.html)をご覧ください。

### Raspberry PIの設定

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