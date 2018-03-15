# 技能模块 Skill
## 智能家居 H5 
### 介绍

智能家居模块是已 H5 的形式集成到 SDK 中，所以必须实现 SDK webbidge 才能正常打开使用此模块。

### URL和环境

* release环境：https://s.rokidcdn.com/homebase/himalaya/index.html#/homes/index
    Rokid Mobile SDK 环境 为 release

* pre环境：https://s.rokidcdn.com/homebase/himalaya/pre/index.html#/homes/index
    Rokid Mobile SDK 环境 为 release

* dev环境：https://s.rokidcdn.com/homebase/himalaya/dev/index.html#/homes/index
    Rokid Mobile SDK 环境 为 Debug

### 接入说明
请参照 SDKWebbridge 的快速集成文档集成 Bridge , 并且必须实现 如下 方法。

Kotlin:

```kotlin

// 响应用户手指按下
override fun touchDown() {
}

// 响应用户手指抬起
override fun touchUp() {
}

// 当前 Webview 打开一个新页面
override fun open(title: String, url: String) {
}

// 在一个新的 Activity （webview） 打开一个新页面
override fun openNewWebView(title: String, url: String) {
}

// 使用 外部浏览器（系统默认浏览器） 打开一个页面
override fun openExternal(url: String) {
}

// 跳回到 一个页面 
override fun goBack(module: String, page: String) {
    if (module == "homebase" && page == "index") {
        // TODO 跳回 智能家居首页，并且清除栈中 其他智能家居页面。 
    }

}

```

字段解释：

| 名称 | 类型 | 必须? | 描述 |
| --- | --- | --- | --- |
| module | String | 是 | 固定值：homebase |
| page | String | 是 | 页面表示：<br>index：智能家居首页 |




