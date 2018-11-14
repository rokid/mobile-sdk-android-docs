# Mobile SDK 集成方式
 
## 导入Mobile SDK

#### 手动导入

1. [下载 Mobile SDK](https://github.com/Rokid/RokidMobileSDKAndroidDemo/tree/master/RokidSDK)

2. 将 com.rokid.mobile.sdk-XXX-XXX.aar 包放入工程的libs目录下，如下图

![](images/sdkLib.png)

3. 在工程的 App Module 的 build.gradle下手动添加依赖，如下代码所示：

```
repositories {
    flatDir {
        dirs 'libs'
    }
}
    
dependencies {
    ......
    compile(name: 'com.rokid.mobile.sdk-XXX-XXX', ext: "aar")
    ......
}
```

#### Gradle 集成

<font color=red size=2>**目前不支持，请敬请期待**</font>

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

## 添加混淆规则

在工程的 proguard-project.txt 里添加以下相关规则：

```
-keep class com.rokid.mobile.** { *; }
```


