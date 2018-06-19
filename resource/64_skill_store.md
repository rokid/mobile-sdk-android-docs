# 技能模块 Skill
## 技能商店 H5 

### URL

* release环境： https://skill.rokid.com/storev2

### 快速接入说明

1、必须 继承 SDKWebview

2、必须实现 如下 方法。


例子:

Kotlin

```kotlin
    // 当前 Webview 打开一个新页面
    override fun open(title: String, url: String) {
    }

    // 在一个新的 Activity （webview） 打开一个新页面
    override fun openNewWebView(title: String, url: String) {
    }

    // 使用 外部浏览器（系统默认浏览器） 打开一个页面
    override fun openExternal(url: String) {
    }
```



