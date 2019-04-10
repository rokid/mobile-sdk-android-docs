# Rokid Mobile SDK 介绍

## 什么是 Rokid Mobile SDK

Rokid Mobile SDK 提供了整套的移动开发支持，能让开发者的移动应用拥有对搭载 Rokid服务的设备配网、指令发送、技能控制、设备管理等交互能力。 

目前支持手机系统有：iOS（苹果）、Android（安卓）。

## 文档介绍

本文档提供了 Rokid Mobile SDK Android 版的接入流程、权限申请、SDK 集成方式、SDK 初始化、各个模块的API说明以及Demo代码。

本文档统一称 Rokid Mobile SDK 为 Mobile SDK

## 接入流程

![mobileSdkFlo](res/media/mobileSdkFlow.png)

#### 1、申请开发者

需先在[开放平台](https://developer.rokid.com)注册一个帐号，并联系 对接的项目经理 申请 AppKey、AppSecrect 和 accessKey。

#### 2、集成 Mobile SDK

[Mobile SDK 集成说明](/res/10_use_sdk.html)

#### 3、开发调试

可以使用如下开关，进入测试环境和调试功能：

```Java
RokidMobileSDK.debug();
```

#### 4、发布上线

开发完成并且进行严格测试的 APP，即可正常上线使用。

## 支持

[Rokid Mobile SDK Android Issue](https://github.com/Rokid/RokidMobileSDKAndroidDemo/issues)


