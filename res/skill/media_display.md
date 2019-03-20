# 媒体模块

## Skill首页
 请求参数：
 
| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| skillId | String | 是 | 当前技能ID |
| callback | Callback | 是 | 请求结果回调 |
示例：

```java
 private fun requestHomeIntent() {
        RokidMobileSDK.media().requestHomeIntent(skillId, object : IGetMediaHomeDataCallBack {
            override fun onSucceed(data: MediaHomeV3Data?) {
            
            }

            override fun onFailed(errorCode: String?, errorMsg: String?) {
               
            }

        })
    }
```
MediaHomeV3Data具体格式如下：

```
格式：
{
  ....
  "version": "3.0.0", // 必须
  "data": {
    "title": "故事",
    "components": [
      {
        "type": "search/banner/row/category/copyright",
        "style": "default/planA/planB",
        "seq": 0,
        "template": "Template String"
      }
    ],
    "auth":{
        "style":"default/planA/planB"
        "imageUrl":"xxxx.png",
        "title":"绑定账号获取QQ音乐服务",
        "content":"绑定账号即可享有QQ音乐内容",
        "button":{
            "text":"去绑定",
            "linkUrl":"xxxx"
        }
    }
  }
}
例子:
{
  ....
  "version": "3.0.0", // 必须
  "data": {
    "title": "故事",
    "components": [
      {
        "type": "search",
        "style": "default",
        "template": "{\"search\": {\"hint\":\"搜索歌曲或者歌手\",\"preview\": {\"title\": \"“你可以对我说”\",\"tips\": [\"“若琪，我想听陈奕迅的十年”\",\"“若琪，收藏这首歌”\",\"“若琪，播放我收藏的歌”\",\"“若琪，我要听周杰伦的歌”\",\"“若琪，放英文歌”\"]}},\"buttons\": [{\"imageUrl\": \"https:\/\/s.rokidcdn.com\/history.png\",\"linkUrl\": \"rokid:\/\/media\/v3\/history?style=default&appId=XXX&dataType=XXX&title=XXX\"},{\"imageUrl\": \"https:\/\/s.rokidcdn.com/favorite.png\",\"linkUrl\":\"rokid:\/\/media/v3/favorite?style=default&appId=XXX&dataType=XXX&title=XXX\"}]}"
      },
      {
        "type": "banner",
        "style": "default",
        "template": "[{\"imageUrl\": \"https:\/\/s.rokidcdn.com\/aaaa.png\",\"linkUrl\": \"rokid:\/\/media/v3/search\"},{\"imageUrl\": \"https:\/\/s.rokidcdn.com\/aaaa.png\",\"linkUrl\": \"rokid:\/\/media/v3/search\"},{\"imageUrl\": \"https:\/\/s.rokidcdn.com\/aaaa.png\",\"linkUrl\": \"rokid:\/\/media/v3/search\"},]"
      }
      ...
    ]
  }
}
```

---

## 专辑列表页
 请求参数：
 
| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| skillId | String | 是 | 当前技能ID |
| groupId | String | 是 | 当前专辑ID |
| startIndex | int | 否 | 分页使用 |
| endIndex | int | 否 | 分页使用 |
| extend | String | 否 | 拓展字段 |
| callback | Callback | 是 | 请求结果回调 |
示例：

```java
 private fun requestListIntent() {
        RokidMobileSDK.media().requestListIntent(skillId,
        groupId,
        startIndex,
        endIndex,
        extend,
        object : IGetMediaListDataCallBack {
            override fun onSucceed(data: MediaListV3Data?) {
            
            }

            override fun onFailed(errorCode: String?, errorMsg: String?) {
               
            }

        })
    }
```
MediaListV3Data具体格式如下：

```json
{
  ...
  "version": "3.0.0",
  "data": {
    "title": title,
    "pageEnd": false,
    "items": [
      {
        "id": "e32d9e56bb5340dc8d1d178cffaadcf3",
        "type": "link",
        "imageUrl": "rokid://s.rokidcdn.com/sss.png",
        "imageType": "circle",
        "title": "稻香",
        "subtitle": "周杰伦",
        "enable": true,
        "linkUrl": "rokid://media/v3/detail?appId=XXX&dataType=XXX&categoryId=XXX",
        "infos": [
            {
             "title": "xxx",
             "iconUrl": "xxxx"
            }
          ],
        "extend": "{\"name1\" : \"value1\", \"name2\" : \"value2\"}"
      },
      ...
    ]
  }
}
```

---

## 专辑详情页
 请求参数：
 
| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| skillId | String | 是 | 当前技能ID |
| groupId | String | 是 | 当前专辑ID |
| startIndex | int | 否 | 分页使用 |
| endIndex | int | 否 | 分页使用 |
| order | String | 否 | 正逆序，asc/desc，目前限喜马拉雅 |
| extend | String | 否 | 拓展字段 |
| callback | Callback | 是 | 请求结果回调 |
示例：

```java
 private fun requestDetailIntent() {
        RokidMobileSDK.media().requestDetailIntent(skillId,
        groupId,
        startIndex,
        endIndex,
        order,
        extend,
        object : IGetMediaWareDetailDataCallBack {
            override fun onSucceed(data: MediaDetailV3Data?) {
            
            }

            override fun onFailed(errorCode: String?, errorMsg: String?) {
               
            }

        })
    }
```
MediaDetailV3Data具体格式如下：

```
{
  ...
  "version": "3.0.0",
  "data": {
    "info": {
      "style": "default",
      "backgroundUrl": "https://s.rokidcdn.com/sss.png",
      "imageUrl": "https://s.rokidcdn.com/sss.png",
      "imageType": "circle",
      "title": "迪士尼经典",
      "subtitle": "",
      "controls": [
        {
          "type": "like/buy",
          "intent": "like_album/have_bought/buy/cancel_ablum",
          "state": false,
          "title": "订阅/购买(¥19.88)/已购买"
        }
      ],
     "copyright:" {
        "summary": "资源由XXXX提供",
        "iconUrl": "" // 保留字段
    },
    "list": {
      "style": "default/planA",
      "pageEnd": false,
      "itemStyle":"default/planA",
      "title": "故事列表（8）",
      "items": [
        {
          "id": "e32d9e56bb5340dc8d1d178cffaadcf3",
          "type": "play",
          "title": "阿拉丁",
          "subtitle": "",
          "enable": true,
          "linkUrl": "",
          "infos": [
            {
             "title": "12",
             "iconUrl": "xxxx"
            }
          ],
          "extend": "{\"name1\" : \"value1\", \"name2\" : \"value2\"}"
        }
      ],
      "more": {
        "tip": "语音一句话收藏：“若琪，收藏”",
        "controls": [
          {
            "type": "like",
            "title": "收藏故事"
          }
        ]
      }
    },
    "extend": "{\"name1\" : \"value1\", \"name2\" : \"value2\"}",
  }
}
```

