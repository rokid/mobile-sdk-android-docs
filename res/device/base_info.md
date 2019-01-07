# 设备基本信息

<font color="red">请先 调用 设备列表 API 后，才能 看到 所属的设备信息，设备信息 已经包含在设备列表中。</font>

SDKDevice 字段说明

| 字段 | 类型  | 备注 |
| --- | ---  | --- |
| deviceId | String | 设备Id  | 
| deviceNick | String | 设备昵称| 
| region | String | 设备地区 | 
| sn | String | 设备Id  | 
| ssid | String | 设备当前连接    Wifi  | 
| ota | String | 系统版本号  | 
| mac | String | mac地址  | 
| ip | String | 设备 IP  | 
| lan_ip | String | 局域网 IP  | 
| device_type_id | String | 设备类型 Id  | 

```json
 {
        // 设备昵称
        "deviceNick": "xxx",   
        // 设备Id          
        "deviceId": "0011111111111111",   
        // 设备地区             
        "region": "CN",
        // 设备 sn 号
        "sn": "02010217020001ED",
        // 设备当前连接 WiFi
        "ssid": "xxx",
        // 系统版本号
        "ota": "2.2.2-20171027.091126",
        // mac地址
        "mac": "02:00:00:00:00:00",
        "ip": "183.129.185.66",
        // 局域网 IP    
        "lan_ip":"192.168.1.156",
        // 自定义TTS音色
        "ttsList": "[{\"name\":\"111777\",\"vibrato\":0,\"speed\":0,\"formant\":0,\"tone\":0},{\"name\":\"234566777777\",\"vibrato\":4,\"speed\":5,\"formant\":-5,\"tone\":5},{\"name\":\"5555\",\"vibrato\":-5,\"speed\":5,\"formant\":-5,\"tone\":-5}]",
        // 系统当前选择TTS音色
        "tts": "{\"formant\":-3,\"speed\":-2,\"tone\":1,\"ttsName\":\"蜡笔小新\"}",
        // 设备类型ID
        "device_type_id":"XXXX"
    }
```

