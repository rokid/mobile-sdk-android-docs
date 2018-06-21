# Rokid Mobile SDK Android版 使用方式 
## SDK 导入方式

<font color=red size=3>**目前只支持手动添加, 后续会添加 Maven**</font>


## 第三方库依赖

Rokid Mobile SDK 目前需要依赖以下 第三方开源库，请添加到自己工程中：

```
compile 'com.google.code.gson:gson:2.8.0'
compile 'com.squareup.okhttp3:okhttp:3.9.0'
compile 'org.greenrobot:eventbus:3.0.0'
compile 'org.greenrobot:greendao:3.2.0'
compile 'org.greenrobot:greendao-generator:3.2.0'
compile 'org.eclipse.paho:org.eclipse.paho.client.mqttv3:1.2.0'
compile 'org.eclipse.paho:org.eclipse.paho.android.service:1.1.1'
```

## 权限依赖

```
<uses-permission android:name="android.permission.INTERNET"/>
<uses-permission android:name="android.permission.BLUETOOTH"/>
<uses-permission android:name="android.permission.BLUETOOTH_ADMIN"/>
<uses-permission android:name="android.permission.READ_PHONE_STATE"/>
<uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION"/>
<uses-permission android:name="android.permission.ACCESS_WIFI_STATE"/>
<uses-permission android:name="android.permission.CHANGE_WIFI_STATE"/>
<uses-permission android:name="android.permission.ACCESS_FINE_LOCATION"/>
<uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION"/>
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE"/>
``` 


