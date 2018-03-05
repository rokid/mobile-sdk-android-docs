# 设备模块 Device 
## 1、获取设备地址位置 

**接口说明**
获取设备的loaction信息

**参数说明**
 
| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| deviceId | String | 是 | 设备ID |

 **示例代码**
 
 ```java
 RokidMobileSDK.device.getLocation(deviceId, new IGetLocationCallback() {
    @Override
    public void onGetLocationSucceed(RKDeviceLocation location) {
        // location从来没有设置过 里面的所有字段都为空
        Logger.i("getLocationByDeviceId", "getLocationSuccess location="+location.toString());
        ... // doSomeing
    }

    @Override
    public void onGetLocationFailed(String errorCode, String errorMsg) {
        Logger.e("getLocationByDeviceId","getLocationFailed errorCode=" + errorCode + " errorMsg=" + errorMsg);
        ... // doSomeing
    }
 });
 ```
 
 **RKDeviceLoaction数据格式**：
 
 ```json
 {
    //邮政编码
    "postalCode": "310023",
    //街道
    "street": "访溪路",
    //身份
    "province": "浙江省",
    //经度
    "longitude": "120.04377191503957",
    //纬度
    "latitude": "30.25401732974572",
    //地区
    "district": "余杭区",
    "locationFrom": "COORDINATES",
    //城市
    "city": "杭州市",
    //国家
    "country": "中国",
    "ip": "183.129.185.66"
}
 
 ```
 
 ---
 
## 修改设备地址位置

**接口说明**
更新设备的 RKDeviceLoaction 信息, RKDeviceLocation 传入更新过的RKDeviceLoaction 对象

**参数说明**
 
| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| deviceId | String | 是 | 设备ID |
| location | RKDeviceLocation | 是 | 设备位置信息 | 

 **示例代码**
 
 ```java
// Location构建示例
RKDeviceLocation location = RKDeviceLocation.newBuilder()
                .country("中国")                   //国家
                .province("浙江省")                //省份
                .city("杭州市")                    //城市
                .district("余杭区")                //区
                .street("访溪路")                  //街道
                .longitude("120.04377191503957")  //经度
                .latitude("30.25401732974572")    //维度
                .ip("183.129.185.66")             //设备ip地址
                .postalCode("310023")             //邮政编码
                .build();
 
 // 更新位置信息
RokidMobileSDK.device.updateLocation(deviceId, location, new IUpdateLocationCallback() {
    @Override
    public void onUpdateLocationSucceed(Location location) {
        Logger.i("onUpdateLocationSuccess location="+location.toString());
        ... // doSomeing
    }

    @Override
    public void onUpdateLocationFailed(String errorCode, String errorMsg) {
        Logger.e("onUpdateLocationFailed errorCode=" + errorCode + " errorMsg=" + errorMsg);
        ... // doSomeing
    }
});
 ```
 
 ---
 

