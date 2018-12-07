# 错误码 Error Code

**错误码说明**：

| errorCode | errorMessage | 说明 |
| :-- | :-- | :-- |
| binder_BT_NAME_EMPTY | device name is empty please check your DeviceName | 传入的name为空 |
| binder_BT_ADDRESS_EMPTY | found device address empty | name对应的address为空 |
| binder_BT_DEVICE_NOT_FOUND | device not found during getRemoteDevice | 发现蓝牙设备失败 |
| binder_BT_PHONE_DISABLE | ble is disable please check bt state | 手机蓝牙在连接过程中关闭 |
| binder_BT_CONNECT_ERROR | ble connect error | 蓝牙连接失败 |
| binder_BT_binder_DATA_ILLEGAL | binderData is illegal please check your userId,wifiSsid,wifiPwd | 发送数据非法: </br> 1.userId不能为空; </br>2.wifiSsid和wifiPwd不能同时为空; </br> 3. DevicebinderData不能为空） |
| binder_BT_SERVICES_NOT_FOUND | ble remote service not found sdk BTEngine service uuid error | 蓝牙服务获取失败 |
| binder_BT_CHARACTER_NOT_FOUND | ble remote service not found sdk BTEngine character uuid error | 蓝牙服务特征值获取失败 |
| binder_BT_DISCONNECT | ble has been disConnect | 蓝牙断开连接 |
| binder_BT_SEND_DATA_ERROR | ble writeCharacteristi error during sendbinderData | 蓝牙写入数据过程中失败 |
| ping_device_RC_DISCONNECT | ble writeCharacteristi error during sendbinderData | SDK与系统长连接断开 |
| ping_device_ID_EMPTY | get device status fail,deviceId is null | 设备ID为空 |
| ping_device_USER_ID_EMPTY | ble writeCharacteristi error during sendbinderData | 用户ID为空 |
| ping_device_SAME_TASK_RUNNING | ble writeCharacteristi error during sendbinderData | 相同的ping个线程在运行 |


