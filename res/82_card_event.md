# 接收卡片消息

## 流程

![](media/vui_card.png)

### 接收 Card 消息

监听Card event 消息

 **示例代码**：
 
```java
@Subscribe(threadMode = ThreadMode.BACKGROUND)
public void onReceivedCard(CardMsgBean cardMessage) {
    Logger.d("Receiver the Card message event: ", cardMessage.toString());
    if (TextUtils.isEmpty(cardMessage.getMsgTxt())) {
        Logger.e("This card message is invalid.");
        return;
    }
    // ......         
}
```

**消息的格式**：
 
 ```json
{
    //card Id
    "dbId": 0,
    //应用的appid        
    "from": "E33FCE60E7294A61B84C43C1A171DFD8",
    //用户的id
    "to":"userId",
    //时间戳
    "msgStamp": "Dec 14, 2017 4:22:24 PM",
    //消息内容（5.4会详细说明）
    "msgTxt": "{\"type\":\"Chat\",\"template\":\"{\\\"tts\\\":\\\"我是若琪，很高兴认识你\\\"}\",\"feedback\":{\"voiceUrl\":null,\"voice\":\"你好\"},\"appid\":\"E33FCE60E7294A61B84C43C1A171DFD8\"}",
    "topic": "card"
}
 ```
 
---
 

