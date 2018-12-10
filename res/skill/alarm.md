# 技能模块 Skill

## 闹钟 Alarm

### 流程

![](media/alarm.png)

### 获取闹钟列表

请求获取设备上的闹钟列表：

Java:

```Java
RokidMobileSDK.skill.alarm().getList(deviceId, new GetAlarmListCallback {
    @override 
    public void onSucceed(List<SDKAlarm> alarmList) {
        //...
    }

    @override 
    public void onFailed(String errorCode, String errorMessage) {
        //...
    }
})
```

Kotlin:

```kotlin
RokidMobileSDK.skill.alarm().getList(skill_alarm_device_id.selectedItem.toString(), 
    object : GetAlarmListCallback {
         override fun onSucceed(alarmList: MutableList<SDKAlarm>?) {
            // ...
         }

         override fun onFailed(errorCode: String?, errorMessage: String?) {
            // ...
         }
     })
```

SDKAlarm 字段说明：

| 参数 | 类型 | 必要？ | 说明 |
| --- | --- | --- | --- |
| id |  int| 是 | 闹钟Id |
| year | int | 是 | 年 |
| month | int | 是 |  月|
| day | int | 是 | 日 |
| hour | int | 是 | 小时 |
| minute | int | 是 | 分钟 |
| repeatType | String | 是 | 重复模式 |
| repeatText | String | 是 | 重复模式的文案 |
| ext | Map<String, String> | 是 | 扩展字段，根据自己业务进行扩展 |

<font color='red'>
注：目前只有Lua版Linux系统支持该字段
    ext字段是手机App与系统通信特有的字段，添加或修改时传入，获取列表时原样返回，以下划线_开始的key是预定义key。
    ext字段可以为空；因为暂时没有删除字段的接口，所以修改时(SpecificTime)需要传入所有的key和value。
  系统不支持时间完全相同的闹钟，所以更新和删除时不会校验ext是否匹配。
</font>

| 名称 | 类型 | 描述 |
| --- | --- | --- |
| _ringtone | string | 闹钟铃声地址，会覆盖全局的闹钟主题 |

<font color='red'>
第三方需求可以由他们自定义字段，比如小雅小雅的标签需求
</font>

---

### 添加闹钟
添加一个闹钟。

Java:

```Java
SDKAlarm alarm = SDKAlarm.builder()
        .year(2018)
        .month(3)
        .day(3)
        .hour(14)
        .minute(30)
        .repeatType(SDKRepeatType.EVERY_MONDAY)
        .build();

RokidMobileSDK.skill.alarm().add(deviceId, alarm);
```

Kotlin:

```Kotlin
val sdkAlarm = SDKAlarm().apply {
      year = 2018
      month = 3
      day = 3
      hour = 14
      minute = 30
      repeatType = SDKRepeatType.EVERY_MONDAY
  }

  RokidMobileSDK.skill.alarm().add(deviceId!!, sdkAlarm)
```

SDKRepeatType 解释：

```
SDKRepeatType.ONCE // 仅此一次
SDKRepeatType.EVERYDAY // 每天
SDKRepeatType.WEEKDAY // 工作日
SDKRepeatType.WEEKEND // 每周末
SDKRepeatType.EVERY_MONDAY // 每周一
SDKRepeatType.EVERY_TUESDAY // 每周二
SDKRepeatType.EVERY_WEDNESDAY // 每周三
SDKRepeatType.EVERY_THURSDAY // 每周四
SDKRepeatType.EVERY_FRIDAY // 每周五
SDKRepeatType.EVERY_SATURDAY // 每周六
SDKRepeatType.EVERY_SUNDAY // 每周日
```

---

### 删除一个闹钟
删除一个闹钟：
 
Java:
 
```java
RokidMobileSDK.skill.alarm().delete(deviceId, alarm, new IChannelPublishCallback() {
    @Override
    public void onSucceed() {
        // TODO
    }

    @Override
    public void onFailed() {
        // TODO
    }

});
```

Kotlin:

```kotlin
RokidMobileSDK.skill.alarm().delete(deviceId, alarm, object : IChannelPublishCallback {
    override fun onSucceed() {
        // TODO
    }

    override fun onFailed() {
     // TODO
    }

})
```
 
注：字段说明 请参考上面 6.1.1
 
---

### 更新闹钟
更新一个闹钟：

Java:

```Java
RokidMobileSDK.skill.alarm().update(deviceId, oldAlarm, newAlarm, new IChannelPublishCallback() {
    @Override
    public void onSucceed() {
        // TODO
    }

    @Override
    public void onFailed() {
        // TODO
    }

});
```
 
Kotlin:

```kotlin
RokidMobileSDK.skill.alarm().update(deviceId, oldAlarm, newAlarm, object : IChannelPublishCallback {
    override fun onSucceed() {
        // TODO
    }

    override fun onFailed() {
     // TODO
    }

})
```
 
注：字段说明 请参考上面 1 和 2
 
---


