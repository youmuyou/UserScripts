HTML5视频截图器
=========================

[脚本发布页](https://greasyfork.org/zh-CN/scripts/370819)

[个人脚本仓库](https://github.com/indefined/UserScripts)

[问题反馈到这里](https://github.com/indefined/UserScripts/issues)

**提交问题前请仔细读完说明和使用须知**

-------------------------
## 功能

- 检测网页中的HTML5视频
- 自动将所选中视频滚动到视野中
- HTML5视频控制(暂停/播放/速度控制/步进)
- 视频截图(png格式原始视频画面)
- jpg截图压缩并自动下载(适用于部分视频和浏览器)
- 快捷键支持

![功能界面](https://greasyfork.org/system/screenshots/screenshots/000/017/198/original/HTML5VideoCapture.capture.jpg)

## 使用说明

- 脚本启动：使用脚本管理器（目前确认Tampermonkey、Violentmonkey可用）安装脚本
  - 方法1：使用快捷键启动，默认为`ctrl+alt+a`，打开工具栏后可自行设置快捷键和作用范围
  - 方法2：在脚本管理器按钮上点击‘启用HTML5视频截图器’打开工具栏
  - ![脚本启动](https://greasyfork.org/system/screenshots/screenshots/000/011/875/original/HTML5VideoCapture.TM.jpg) ![脚本启动](https://greasyfork.org/system/screenshots/screenshots/000/011/876/original/HTML5VideoCapture.VM.jpg)

- 视频识别
  - 工具栏启动会自动检测网页中存在的HTML5视频并选中第一个视频作为操作对象
  - 如页面内容变更，点击工具栏上的检测按钮可以重新检测网页中的视频
  - 如果网页中存在多个视频，从下拉框中选择需要操作的对象，被选中的视频会自动滚动到视野内

- 视频控制：目前工具栏提供播放/暂停、视频速度、视频步进三种类型功能对视频进行操作
  - 具体功能将鼠标指针悬停在按钮上会有相应功能提示
  - 并不一定对所有视频管用，不同网页表现差异较大，具体问题请看[使用须知](#使用须知)

- 截图
  - 如果视频源和浏览器支持，点击截图右侧的↓箭头可以直接下载一张jpg格式截图，体积较小
  - 如果视频或者浏览器不支持，点击↓箭头和点截图一样会打开一个新窗口显示当前视频画面，在画面上右键另存可得到png格式原始截图
  - 或许你也可以拿它来截一些直播，不过适用性应该会比截普通视频差，控制按钮也不一定生效

- 快捷键设置
  - 点击工具栏下部的扩展箭头打开设置框，具体设置意义请将鼠标悬停在对应文本框或者按钮上查看提示
  - 全局视频快捷键默认不勾选，且对部分视频可能无效甚至可能冲突，建议针对不同网站设置

-------------------------
## 兼容性

- 本脚本使用了较新的ES6+和HTML5 API，比较旧的浏览器版本可能不兼容
- chrome 72 @ Tampermonkey 4.7/4.8 测试通过
- firefox 64 @ Tampermonkey 4.8 、Violentmonkey v2.10 测试通过
- 在启用内容安全策略的网站上只有Tampermonkey可用，且TM高级设置中注入CSP必须开启（默认启用）
- 不兼容Greasemonkey4，原因未知，虽然做了兼容理论可用但是总之用不了也没信息可以调试
- 大概不兼容书签、第三方浏览器原生扩展方式使用

-------------------------
## 使用须知

- 对大部分HTML5视频有效(CSP见兼容性)，不支持FLASH和其它播放插件。如果有明确不支持的HTML5视频请提交反馈
- 如果播放器在播放过程中发生变更(换源或重载)脚本可能会操作失败，此时一般重新检测可以解决
- 检测到的视频并不一定都是你能看到的，可能会有一些隐藏视频或空视频标签，自行在下拉框中寻找合适的进行操作
- 截取到的图片尺寸为视频的原始大小，和当前播放器窗口大小无关，不会包含播放暂停按钮、弹幕等非视频内的内容
- 新建页面打开截图可能会被浏览器拦截，如果浏览器有弹出窗口警告需要先允许弹出窗口再重新截图
- 直接下载截图并不一定对所有视频和浏览器有效，有时可能和点截图按钮效果一样，甚至可能点了完全没有反应
- 播放暂停控制按钮不一定对所有视频生效，或者有时生效但是在网页上会表现很怪异(比如转圈遮罩层/弹幕没停止)
- 逐帧控制会暂停视频，同上一条原因可能对有些视频无效，如果逐帧后自动播放可以尝试点击播放器自己的暂停再操作
- 逐帧控制使用60fps帧率，实际控制可能不是逐帧的，控制时画面可能不会实时响应，特别是点太快时要等播放器缓过来
- 使用快捷键时工具栏可能并不会响应，也没有提示
