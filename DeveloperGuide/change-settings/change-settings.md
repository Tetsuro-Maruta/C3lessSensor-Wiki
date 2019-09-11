# 設定の変更方法

## はじめに

本項目では、本システムの簡単な変更方法を紹介します。設定は、以下のコマンドから変更することができます。

```
cd C3lessSensorSystem/sensorSystem
nano settings.yml
```

ファイルは次のような構成になっております。
```
Resources:
  Globals:
    #constants of serial
    SerialSpeed: 115200
    SerialTimeOut: 1
    #wating time 
    WaitTime: 0.001
    #format of timestamp
    TimestampFormat: '%Y/%m/%d %H:%M:%S'
    #path of YAML file which about sensor
    SensorDefinisionYAML: /home/pi/C3lessSensorSystem/sensorSystem/sensor-data.yml
    Log:
      #choose from DEBUG, INFO, WARNING, or ERROR
      logLevel: INFO
      logFormat: "%(asctime)s %(levelname)s %(message)s"
      logFile: "/home/pi/C3lessSensorSystem/sensorSystem/log/sensorSystem.log"

  AWSIoT:
    #使用する場合はTrueにする。使用しない場合はFalse.以下同様
    Usage: False
    Parameters:
      CertsPath: /home/pi/C3lessSensorSystem/sensorSystem/certs
      TopicFilter: <YOUR_TOPIC_FILTER>
      ClientName: <YOUR_CLIENT_NAME>
      EndPoint: <YOUR_ENDPOINT>

  M2X:
    Usage: False
    Parameters:
      CalcData: False
      DeviceID: ""
      APIKey: ""
  
  LocalSave:
    Usage: True
    Parameters:  
      CalcData: True
      #USBメモリなど外部ストレージをマウントする場合は、/media/pi
      SavePath: '/media/pi'
      #SavePathで指定したディレクトリに直接保存するかどうか設定する。
      #Trueならば、直下に、Falseなら保存可能なディレクトリを探索し、
      #保存する。
      SaveDirectory: False
      
  #User defined API
  Other:
    Services:
      APIKey: ""
      URL: ""
    
```


## 内容の説明

ここでは、各項目についての説明を行います。

### Globals

ここでは、共通の設定を変更することができます。

#### SerialSpeed(初期値 115200)

シリアルポートのボーレート(baudrate)を設定する事ができます。

#### SerialTimeOut

シリアルポートのタイムアウト時間を設定することができます。

#### WaitTime(0.001sec=1msec)

プログラムのスリープ時間を設定します。初期値は1 msecです。


