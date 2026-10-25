# 校园巡检（实验三）

Android 工程结构与巡检页面整理实验。基于实验二的 Kotlin Compose 工程，完成三文件拆分、OkHttp 接入与真实 HTTPS 请求验证。

## 运行方法

1. Android Studio 打开工程，等待 Gradle Sync 完成
2. 连接模拟器或真机
3. 点击 Run 运行，桌面应用名称显示"校园巡检"
4. 点击"请求 A203"按钮发起 `https://httpbin.org/get?room=A203`，页面底部显示状态码与回显
5. 点击"请求 A204"按钮发起带 A204 参数的请求，对比回显中 `args.room` 的变化

## 三个源码文件职责

| 文件 | 职责 |
|---|---|
| `MainActivity.kt` | 系统入口，设置 Compose 内容，安排请求线程与结果回传 UI |
| `InspectionScreen.kt` | 巡检页面显示（巡检员、实验室、设备数统计），按钮与请求回调，计算未检查数量 |
| `InspectionNetwork.kt` | 创建 OkHttpClient，执行 HTTPS 请求，处理响应与异常 |
