# Vui 反馈 模块

## 获取Card 列表
默认一次拉取25条
 
 **参数说明**
 
| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| maxDbId | int | 是 | card的id  |
| pageSize | int | 是 | 分页大小  |

 **示例代码**：
 
 ```java
 RokidMobileSDK.vui.getCardList(maxDbId,pageSize,new IGetCardsCallback() {
            @Override
            public void onGetCardsSucceed(final List<CardMsgBean> cardInfoList, boolean hasMore) {
                Logger.d("getCardListFromService success ");
                if (CollectionUtils.isEmpty(cardInfoList) || !hasMore) {
                    Logger.d("getCardListFromService success but card list is empty or hasMore false");
                    // 服务端没有更多数据了
                    } else {
                    // 拿到cards
                    }
            }

            @Override
            public void onGetCardsFailed(String errorCode, String errorMsg) {
                Logger.e("getCardListFromService Failed errorCode=" + errorCode + " ;errorMsg=" + errorMsg);
                // ...
            }
        });
 ```
 
  **返回参数说明**
 
| 字段    | 类型    | 说明 |
| ------ | ------- |  ----- |
|cardInfoList| List|card列表，按照时间的顺序排列（最新的card在数组尾端） |
| hasMore | boolean | 服务端是否还有数据 |
  
---

