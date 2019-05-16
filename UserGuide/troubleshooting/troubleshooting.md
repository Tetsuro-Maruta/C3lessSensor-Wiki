# 本プログラムが動作しないときは
## はじめに
本プログラムが動作しないときは、以下の事項を確認してください。

- [[ハードウェアを確認する|check-hardware]]
- [[ソフトウェアを確認する|check-software]]

以上をすべて実行した上で、解決しない場合は、以下のコマンドを実行し、その結果を本ページの[Issues](https://github.com/Tycoh/C3lessSensorSystem/issues/new)に投稿をお寄せください。

```
sudo systemctl status sensorSystem

less [ログが格納されているパス]/sensorSystem.log | grep ERROR
```