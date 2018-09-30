# 设备消息

## 当前选择的设备发生变化

### 消息体

EventCurrentDeviceChange

### 例子

Kotlin

```kotlin
@Subscribe(threadMode = ThreadMode.BACKGROUND)
public fun onReceived(eventCurrentDeviceChange: EventCurrentDeviceChange){
    // TODO
}
```

EventCurrentDeviceChange 说明：

| 参数 | 类型 | 说明 |
| --- | --- | --- |
| deviceId | String | 当前设备Id |
 
---

## 当前设备状态发生变化

### 消息体

EventCurrentDeviceStatus 

### 例子

Kotlin

```kotlin
@Subscribe(threadMode = ThreadMode.BACKGROUND)
public fun onReceived(eventCurrentDeviceStatus: EventCurrentDeviceStatus){
    // TODO
}
```
 
EventCurrentDeviceStatus 说明：

| 参数 | 类型 | 说明 |
| --- | --- | --- |
| deviceId | String | 当前设备Id |
| isOnline | boolean | 是否在线 |

---

## 设备状态发生变化

### 消息体

EventDeviceStatus

### 例子

Kotlin

```kotlin
@Subscribe(threadMode = ThreadMode.BACKGROUND)
public fun onReceived(eventDeviceStatus: EventDeviceStatus){
    // TODO
}
```

EventDeviceStatus 说明：

| 参数 | 类型 | 说明 |
| --- | --- | --- |
| deviceId | String | 当前设备Id |
| isOnline | boolean | 是否在线 |
 
---

## 设备解绑

### 消息体

EventUnbind

### 例子

Kotlin

```kotlin
@Subscribe(threadMode = ThreadMode.BACKGROUND)
public fun onReceived(eventUnbind: EventUnbind){
    // TODO
}
```

EventUnbind 说明：

| 参数 | 类型 | 说明 |
| --- | --- | --- |
| deviceId | String | 当前设备Id |

---

## 音量发生变化

### 消息体

EventVolumeChange 

### 例子

Kotlin

```kotlin
@Subscribe(threadMode = ThreadMode.BACKGROUND)
public fun onReceived(eventVolumeChange: EventVolumeChange){
    // TODO
}
```

EventVolumeChange 说明：

| 参数 | 类型 | 说明 |
| --- | --- | --- |
| event | String | 固定值：ON_VOLUME_CHANGE |
| from | String | 设备Id |
| to | String | 用户Id |
||||
| volumeTemplate.mediaCurrent | String | 媒体当前音量 |
| volumeTemplate.mediaCurrentmediaTotal | String | 媒体最大音量 |
 
---
 
## 系统更新信息

### 消息体

EventDeviceSysUpdate 

### 例子

Kotlin

```kotlin
@Subscribe(threadMode = ThreadMode.BACKGROUND)
public fun onReceived(eventDeviceSysUpdate: EventDeviceSysUpdate){
    // TODO
}
```
 
| 参数 | 类型 | 说明 |
| --- | --- | --- |
| from | String | 消息来源设备Id |
| to | String | 用户Id |
||||
| versionInfo.getCheckCode | int | 0:表示没有更新 ,1:表示有更新 |
| versionInfo.currentVersion | String | 当前版本 |
| versionInfo.changelog | String | 版本更新信息 |
 
---

