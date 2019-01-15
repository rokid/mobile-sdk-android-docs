# 设备基本信息

<font color="red">请先 调用 设备列表 API 后，才能 看到 所属的设备信息，设备信息 已经包含在设备列表中。</font>

SDKDevice 字段说明

| 字段 | 类型  | 备注 |
| --- | ---  | --- |
| device_type_id | String | 设备类型 Id  | 
| deviceId | String | 设备Id  | 
| sn | String | 设备Id  |
| deviceNick | String | 设备昵称| 
| ssid | String | 设备当前连接    Wifi  | 
| ota | String | 系统版本号  | 
| mac | String | mac地址  | 
| ip | String | 设备 IP  | 
| lan_ip | String | 局域网 IP  | 

```json
 {
        // 设备昵称
        "deviceNick": "xxx",
         // 设备类型ID
        "device_type_id":"XXXX",
        // 设备Id          
        "deviceId": "02010217020001ED",
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
        "lan_ip":"192.168.1.156"
    }
```

