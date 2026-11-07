<h1 align="center">Tokki</h1>

<p align="center">别给 AI 值夜班了，Tokki 帮你看着 Codex。</p>

<p align="center"><a href="README.md">English</a> · <strong>简体中文</strong></p>

<p align="center"><a href="https://github.com/MossAndMaurice/Tokki/releases/tag/macos%2Fv1.12.6.1"><strong>下载 macOS 版</strong></a> · <a href="CHANGELOG.md">版本说明</a></p>

![字牌固定在实心底板上：妈耶，又停了？！Tokki 帮我看着，我睡觉去了！](assets/tokki-hero-3d-zh-CN-v4.png)

睡前给 Codex 布置了任务，想着跑一晚上，早上起来收成果。

早上一看，它早就没额度了。后半夜什么也没干。

**Tokki 就是管这个的。** 它在 Mac 状态栏里运行，盯住选中的会话。额度恢复后，检查原任务的状态，再回到那个会话发一句「继续」。这句话可以在设置里改。

活都交出去了，总不能还得隔一会儿回来看它停没停。

## 具体能干什么

- 在状态栏查看剩余额度和重置时间。
- 记住哪些受监控的会话中断了，逐个检查、尝试恢复。
- 除了额度耗尽，也处理部分 Codex 已放弃重试的连接故障，以及模型满载错误。
- 发送前核对原任务。任务还在跑、有草稿或待处理输入，就不发。
- 检查原会话是否真的启动了新任务。发送结果不明，就不会自动再发一遍。

没额度的时候还是得等，Tokki 绕不过使用限制。

## 安装

**Apple Silicon（M 系列）Mac · macOS 13 及以上**

需要 Codex 桌面应用，以及已安装、已登录的 Codex CLI。**Windows 版即将推出。** 目前没有 Linux 版。

1. 打开 [最新 macOS Release](https://github.com/MossAndMaurice/Tokki/releases/tag/macos%2Fv1.12.6.1)，从 **Assets** 下载 `Tokki-macOS-….dmg`。
2. 打开 DMG，运行 **`Install.command`** 安装或升级。
3. 从状态栏打开 Tokki，给需要自动恢复的会话开启监控。

使用时保持 Tokki、Codex 运行，Mac 也要保持唤醒。设置里可以开启登录时启动。

升级时重新运行安装器即可。它会先请求旧版正常退出，再替换应用，保留设置和恢复记录；无法安全退出就停止安装。

**当前安装包使用 ad-hoc 签名，尚未经过 Apple 公证，macOS 可能阻止打开。** 安装前请看对应版本的说明。

<details>
<summary>使用前还需要知道的事</summary>

Tokki 的设置和恢复记录保存在本机，不改写 Codex 的配置、数据库或会话日志。额度查询和消息提交仍通过 Codex 完成。

自动恢复需要明确的中断证据，并重新核对额度、原会话和原任务。暂时没有输出不会触发恢复。每条恢复计划只允许一次发送尝试，发送前先记到本机；结果不明时不自动重发。

退出 Tokki 后计时停止。它不会唤醒睡眠中的 Mac，也不会启动已关闭的 Codex。重新打开或系统醒来后会再检查。Codex 更新可能影响兼容性。

目前在两条原桌面会话中确认了自然额度恢复成功，尚未完成所有账户切换、睡眠、重启和自然网络故障的完整验证。重复定时问题仍未解决。各版本的验证情况和限制见 Release 说明。

</details>

## 有问题？

[提个 Issue](https://github.com/MossAndMaurice/Tokki/issues)，带上 Tokki、macOS、Codex 的版本，以及具体发生了什么。截图和日志记得删掉凭证、私人会话内容。

这个仓库放安装包和版本说明，不公开应用源码。

## 隐私

**我们不收集、也不上传用户数据。** 会话、代码、凭证、额度信息和本地操作记录不会发送给我们。Tokki 的设置和恢复记录保存在设备上，不做使用统计或遥测。

额度查询和唤醒消息仍通过 Codex 完成，Codex 自身的网络行为和隐私条款继续适用。配置更新仓库后，Tokki 会向 GitHub 查询公开版本，并在请求中携带 Tokki 版本号；请求不包含会话、代码、凭证或恢复记录。

## 版权与使用

**© 2026 Tokki。保留所有权利。**

Tokki 是专有软件，以编译后的安装包形式分发。允许下载、安装和使用官方发布的版本。除适用法律及第三方组件许可证另有规定外，其余权利保留。在这里提供下载，不代表授予 Tokki 源码的开源许可。

<sub>Tokki 是独立项目，与 OpenAI 无隶属关系，也未获其背书。</sub>
