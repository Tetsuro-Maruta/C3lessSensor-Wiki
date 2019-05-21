# 本プログラムが動作しないときは
## はじめに
本プログラムが動作しないときは、以下の事項を確認してください。

- [センサを確認する](checkSensor.md)
- [ハードウェアを確認する](checkHardware.md)
- [ソフトウェアを確認する](checkSoftware.md)

以上をすべて実行した上で、解決しない場合は、以下のコマンドを実行し、その結果を本ページの[不具合報告フォーム](https://github.com/Tycoh/C3lessSensorSystem/issues/new?assignees=Tycoh&labels=bug&template=---------.md&title=BUG)に投稿をお寄せください。

```
sudo systemctl status sensorSystem

less [ログが格納されているパス]/sensorSystem.log | grep ERROR
```