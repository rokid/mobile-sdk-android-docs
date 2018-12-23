# 喜马拉雅 Skill 授权

### 概述

本文档适用用第三方厂商，使用rokid喜马拉雅技能时，需要喜马拉雅token。作用于授权成功后，喜马拉雅token和rokid账户进行绑定

### 准备阶段

在喜马拉雅oauth平台申请appId，appSecret
提供给rokid已经申请的喜马拉雅appId，appSecret。Rokid会分配对应厂商的callback
根据Rokid提供的callback，完善喜马拉雅oauth平台callback地址

### 授权交互

![](media/15455972325497.jpg)

### 喜马拉雅授权 SDK 文档

喜马拉雅 文档：[点击查看](http://open.ximalaya.com/doc/sdk-access)

---

### 使用说明

```Java
RokidMobileSDK.media.thirdAuth().getThirdOauthInfo(ThirdAuth.XMLY,  "deviceTypeId",  new IGetThirdOauthInfoCallback() {
    @Override
    public void onGetThirdOauthInfoSucceed(ThirdOauthInfoBean thirdOauthInfoBean) {
        // TODO 
                       
        // 授权例子
        XmlyAuthInfo xmlyInfo = new XmlyAuthInfo(content, 
            thirdOauthInfoBean.getBaseAppId(),
            thirdOauthInfoBean.getBaseRedirectUri(),
            thirdOauthInfoBean.getXMLYParam());

            XmlySsoHandler ssoHandler = new XmlySsoHandler(ThirdAuthActivity.this, xmlyInfo);
            ssoHandler.authorize(new XMLYAuthListener(callback));
    }

    @Override
    public void onGetThirdOauthInfoFailed(String errorCode, String errorMsg) {
        // TODO
    }
});
```

