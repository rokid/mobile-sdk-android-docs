# Mobile SDK 集成方式
 
## 一、导入Mobile SDK

### 1.1 maven导入（推荐方式）

#### 1.1.1 引入 maven 仓库地址

在工程根目录的 <font color=red>build.gradle </font> 找到（或增加） `allprojects -> repositories` 节点，然后在该节点加入 maven 仓库地址 `https://dl.bintray.com/rokid/maven/`，如下所示：

```
allprojects {
    repositories {
        google()
        jcenter()
        ...
        maven { url "https://dl.bintray.com/rokid/maven/" }
        ...
    }
}
```

#### 1.1.2 依赖最新的 SDK 包

在 Module 的 <font color=red>build.gradle </font> 中找到 `dependencies` 节点，并在该节点加入 SDK 依赖 `implementation 'com.rokid.mobile:sdk:1.x.x'`，如下所示：

```
dependencies {
    ...
    // sdk
    implementation 'com.rokid.mobile:sdk:1.x.x'
    ...
}
```

### ~~1.2 手动导入 (不推荐使用)~~

<font color=red>该引用方式即将废除，请使用 maven 导入的方式。 </font>

1、[下载 Mobile SDK](https://github.com/Rokid/RokidMobileSDKAndroidDemo/tree/master/RokidSDK)

2、将 com.rokid.mobile.sdk-XXX-XXX.aar 包放入工程的libs目录下，如下图

![](media/sdkLib.png)

3、在工程根目录的 <font color=red>build.gradle </font> 中手动添加依赖，如下代码所示：

```
repositories {
    flatDir {
        dirs 'libs'
    }
}
```

4、在 Module 目录下 <font color=red> build.gradle </font> 中添加本地 SDK aar 包依赖，如下所示：

```
dependencies {
    ......
    implementation(name: 'com.rokid.mobile.sdk-XXX-XXX', ext: "aar")
    ......
}
```

## 二、添加 Kotlin 依赖

* 在项目根目录下的 <font color=red>build.gradle </font>中添加

```
buildscript {
    ...
    dependencies {
        ...
        classpath 'org.jetbrains.kotlin:kotlin-gradle-plugin:x.x.x'
        ...
    ...
}
```

* 在 Module 目录下 <font color=red> build.gradle </font> 中添加 Kotlin 插件支持

```
apply plugin: 'kotlin-android'
apply plugin: 'kotlin-android-extensions'
```

* 在 Module 目录下 <font color=red> build.gradle </font> 中导入 Kotlin 支持库

```
dependencies {
        ...
        implementation 'org.jetbrains.kotlin:kotlin-stdlib:x.x.x'
        ...
    ...
```

## 三、添加第三方库依赖

如果配置完前面两个步骤后，工程编译提示某些三方开源库未找到，此时需要您手动添加相关依赖，如果没有出错，则可以直接跳过这一步骤。

Rokid Mobile SDK 目前需要依赖以下第三方开源库，请添加到自己工程中：

```
implementation 'com.google.code.gson:gson:2.8.0'
implementation 'com.squareup.okhttp3:okhttp:3.9.0'
implementation 'org.greenrobot:eventbus:3.0.0'
implementation 'org.greenrobot:greendao:3.2.0'
implementation 'org.greenrobot:greendao-generator:3.2.0'
implementation 'org.eclipse.paho:org.eclipse.paho.client.mqttv3:1.2.0'
implementation 'org.eclipse.paho:org.eclipse.paho.android.service:1.1.1'
```

## 四、添加混淆规则

在工程的 proguard-project.txt 里添加以下相关规则：

```
-keep class com.rokid.mobile.** { *; }
```


