# Autoqqpet（QQ 宠物自动托管）

一个 **libxposed / LSPosed** 模块，用于自动化 QQ 宠物。它会按"有效属性收益"来规划每天的
学习 / 工作 / 冒险，兼顾疲劳度并让金币自给自足；同时处理喂食、洗澡、购买食物、PK 与访问好友。
模块还带一个保活前台服务：实时状态通知 + 看门狗，当 QQ 心跳超时（被杀/冻结）时自动把 QQ 拉起来。

> ⚠️ 实验性工具。自动化游戏可能违反用户协议并带来账号风险，请自行评估、自担风险。

## 运行环境
- 框架：**LSPosed** 或 **Vector**（libxposed API 102，静态作用域 staticScope）
- 系统：Android 8.0 及以上（minSdk 26）
- 目标应用：**com.tencent.mobileqq**（QQ）

## 使用步骤
1. 安装并激活 LSPosed / Vector 框架；
2. 安装本模块 APK；
3. 在框架中启用本模块，并把作用域设为 **QQ（com.tencent.mobileqq）**（已为你预勾选）；
4. 打开 **Autoqqpet**，阅读并同意用户协议，选择目标属性并开启自动托管；
5. 通知栏会实时显示它在做什么；详细日志见 logcat，标签 `Autoqqpet`。

## 功能说明
- 日程规划：按有效属性收益择优安排 学习 / 工作 / 冒险，带每日上限与疲劳处理；学工不划算时优先冒险。
- 日常照顾：喂食、洗澡、购买食物；PK 与访问好友，附带好友黑白名单与每日次数上限。
- 精准调度：用 AlarmManager 定点唤醒、到期准确结算、失败有界重试。
- 保活：前台服务 + 唤醒锁（PARTIAL_WAKE_LOCK）+ 实时状态通知 + 看门狗（心跳超时自动拉起 QQ 并补发 auto 指令）；开机自启。

## 许可
本模块为**专有 / 闭源**软件。此仓库发布的二进制仅供通过在线仓库安装使用；未经许可不得二次分发或逆向。详见应用内用户协议（EULA）。

## 反馈支持
请在本仓库提交 issue：
https://github.com/Xposed-Modules-Repo/com.juwanh.autoqqpet/issues
