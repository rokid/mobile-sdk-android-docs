# 技能模块 Skill
## 提醒 Remind
### 1、提醒列表
请求获取设备上的提醒列表：

```Java
RokidMobileSDK.skill.remind().getList(deviceId)
```

接收到Event：

```Java
@Subscribe(threadMode = ThreadMode.MAIN)
public void onRemindResponse(EventRemindBean eventRemind) {
    // ...
}
```

EventAlarmBean 字段说明：

| 参数 | 类型 | 必要？ | 说明 |
| --- | --- | --- | --- |
| alarmList | List<AlarmContentBean> | 否 | 提醒列表 |

AlarmContentBean 字段说明：

| 参数 | 类型 | 必要？ | 说明 |
| --- | --- | --- | --- |
| id |  int| 是 | 闹钟Id |
| year | int | 是 | 年 |
| month | int | 是 |  月|
| day | int | 是 | 日 |
| hour | int | 是 | 小时 |
| minute | int | 是 | 分钟 |
| content | String | 是 | 提醒内容 |
| ext | Map<String, String> | 是 | 扩展字段，根据自己业务进行扩展 |

---

### 2、删除一个提醒
删除一个提醒：
 
```Java
RokidMobileSDK.skill.remind().delete(deviceId, alarmContentBean);
```
 
注：字段说明 请参考上面 1

---

