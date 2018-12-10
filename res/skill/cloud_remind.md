# 技能模块 Skill

## 提醒 Remind

### 提醒列表

请求获取设备上的提醒列表：

Java:

```Java
RokidMobileSDK.skill.cloudRemind().getList(deviceId, new SDKGetRemindListCallback {
    @override 
    public void onSucceed(List<SDKRemind> remindList) {
        // ...
    }
    
    @override
    public void onFailed(String: errorCode, String errorMessage) {
        // ...
    }
})
```

Kotlin:

```kotlin
RokidMobileSDK.skill.cloudRemind().getList(deviceId, object : SDKGetRemindListCallback {
    override fun onSucceed(remindList: MutableList<SDKRemind>?) {
        // ...
    }
    
    override fun onFailed(errorCode: String?, errorMessage: String?) {
        //...
    }
})
```

SDKRemind 字段说明：

| 参数 | 类型 | 必要？ | 说明 |
| --- | --- | --- | --- |
| id |  int| 是 | 提醒Id |
| year | int | 是 | 年 |
| month | int | 是 |  月|
| day | int | 是 | 日 |
| hour | int | 是 | 小时 |
| minute | int | 是 | 分钟 |
| repeatType | String | 是 | 重复模式 |
| repeatText | String | 是 | 重复模式文案 |
| content | String | 是 | 提醒内容 |
| ext | Map<String, String> | 是 | 扩展字段，根据自己业务进行扩展 |

---

### 删除一个提醒

删除一个提醒：
 
Java:

```Java
RokidMobileSDK.skill.cloudRemind().delete(deviceId, remind, new SDKOperateAlarmCallback() {
    @Override
    public void onSucceed() {
        // TODO
    }

    @Override
    public void onFailed(String errorCode, String errorMessage) {
        // TODO
    }

});
```

Kotlin:

```kotlin
RokidMobileSDK.skill.cloudRemind().delete(deviceId, remind, object : SDKOperateAlarmCallback {
    override fun onSucceed() {
        // TODO
    }

    override fun onFailed(errorCode: String?, errorMessage: String?) {
     // TODO
    }

})
```
 
注：字段说明 请参考上面 1

---

