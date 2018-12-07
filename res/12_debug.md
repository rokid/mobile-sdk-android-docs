# Mobile SDK 调试

开发者可以 切换到 测试环境，并打印一些日志用于分析问题。

## SDK 环境

调用这个 API 可以切换到 线上、预发、测试环境，方便调试开发。

参数说明

| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| env  | SDKEnvType | 是 | SDK环境：<br> SDKEnvType.RELEASE 线上环境;<br> SDKEnvType.PRE 预发环境;<br>SDKEnvType.DEV 测试环境 |

举个大栗子

Kotlin

```Kotlin
RokidMobileSDK.env(SDKEnvType.PRE)
``` 

## SDK Log

打开日志输出

举个大栗子

Kotlin

```Kotlin
RokidMobileSDK.openLog(true)
``` 

