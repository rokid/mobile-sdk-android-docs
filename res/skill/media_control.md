# 媒体模块

## 播放

 请求参数：
 
| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| skillId | String | 是 | 当前技能ID |
| id | String | 是 | 待播放的媒体ID |
| callback | Callback | 是 | 请求结果回调，可为null |
示例：

```java
private fun requestPlayIntent() {
        RokidMobileSDK.media().requestPlayIntent(skillId,
                id,
                object : IMediaWareControlCallback {
                    override fun onSucceed(data: MediaWareControlData?) {
                
                    }

                    override fun onFailed(errorCode: String?, errorMsg: String?) {
                    
                    }
                })
    }
```
MediaWareControlData具体格式如下：

```
{
    "deviceId": "0201021712001400",
    "masterId": "2F6CF9622BA60B9290089C3EF5C9E7E2",
    "requestId": "73d81c4134974404af9f3b967baf99fc",
    "success": true,
    "version": "3.0.0"
}
```

---

## 暂停

 请求参数：
 
| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| skillId | String | 是 | 当前技能ID |
| callback | Callback | 是 | 请求结果回调，可为null |
示例：

```java
private fun requestPauseIntent() {
        RokidMobileSDK.media().requestPauseIntent(skillId,
                object : IMediaWareControlCallback {
                    override fun onSucceed(data: MediaWareControlData?) {
                
                    }

                    override fun onFailed(errorCode: String?, errorMsg: String?) {
                    
                    }
                })
    }
```

---

## 继续播放

 请求参数：
 
| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| skillId | String | 是 | 当前技能ID |
| callback | Callback | 是 | 请求结果回调，可为null |
示例：

```java
private fun requestResumeIntent() {
        RokidMobileSDK.media().requestResumeIntent(skillId,
                object : IMediaWareControlCallback {
                    override fun onSucceed(data: MediaWareControlData?) {
                
                    }

                    override fun onFailed(errorCode: String?, errorMsg: String?) {
                    
                    }
                })
    }
```

---

## 上一首

 请求参数：
 
| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| skillId | String | 是 | 当前技能ID |
| callback | Callback | 是 | 请求结果回调，可为null |
示例：

```
private fun requestPreviousIntent() {
        RokidMobileSDK.media().requestPreviousIntent(skillId,
                offset,
                object : IMediaWareControlCallback {
                    override fun onSucceed(data: MediaWareControlData?) {
                
                    }

                    override fun onFailed(errorCode: String?, errorMsg: String?) {
                    
                    }
                })
    }
```

---

## 下一首

 请求参数：
 
| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| skillId | String | 是 | 当前技能ID |
| callback | Callback | 是 | 请求结果回调，可为null |
示例：

```
private fun requestNextIntent() {
        RokidMobileSDK.media().requestNextIntent(skillId,
                offset,
                object : IMediaWareControlCallback {
                    override fun onSucceed(data: MediaWareControlData?) {
                
                    }

                    override fun onFailed(errorCode: String?, errorMsg: String?) {
                    
                    }
                })
    }
```
以上4个接口的需要订阅以下事件，收到事件后才表示当前的操作是真的执行成功：

```
 @Subscribe(threadMode = ThreadMode.MAIN)
    public void onMediaPlayInfo(SDKMediaEvent sdkMediaEvent) {
    
    }
```
SDKMediaEvent的具体格式如下：

```
{
  "appId": "xxx",
  "event": "xxx",
  "version": "3.0.0", // 必须
  "template": {
    "style": "default/planA",
    "titleButtons": [
      {
        "imageUrl": "https://s.rokidcdn.com/sss.png",
        "linkUrl": "rokid://media/v3/detail?appId=XXX&dataType=XXX&groupId=XXX"
      }
    ],
    "item": {
      "id": "e32d9e56bb5340dc8d1d178cffaadcf3",
      "imageUrl": "rokid://s.rokidcdn.com/sss.png",
      "title": "稻香",
      "subtitle": "周杰伦",
      "offset": "60",
      "duration": "360",
      "extend": "{\"name1\" : \"value1\", \"name2\" : \"value2\"}"
    },
    "controlInfo": {
      "like": true,
      "loop": true,
      "state": "playing"
    },
    "copyright:" {
        "summary": "资源由XXXX提供",
        "iconUrl": "" // 保留字段
    }
}

```

---

## 当前播放信息

 请求参数：
 
| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| skillId | String | 是 | 当前技能ID |
| callback | Callback | 是 | 请求结果回调，可为null |
示例：

```java
private fun requestPlayInfoIntent() {
        RokidMobileSDK.media().requestPlayInfoIntent(skillId,
                object : IMediaPlayInfoCallback {
                    override fun onSucceed(data: MediaEventTemplate?) {
                        
                    }

                    override fun onFailed(errorCode: String?, errorMsg: String?) {
                    
                    }
                })    
}
```
该接口需要订阅以下事件：

```
 @Subscribe(threadMode = ThreadMode.MAIN)
    public void onMediaPlayInfo(SDKMediaEvent sdkMediaEvent) {
    
    }
```


