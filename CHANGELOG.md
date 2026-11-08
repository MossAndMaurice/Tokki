# Release notes · 更新日志

## macOS 1.12.8.2 — 2026-11-08

## 中文

本次仅递增交付版本，应用行为与 1.12.8.1 相同。已安装 1.12.8.1 的用户可在设置中点击“开始更新”，亲自验证按钮下载百分比、关闭界面后继续下载，以及校验后的静默安装与自动重启。

使用时保留 Tokki 后台进程；关闭窗口即可，退出 Tokki 会停止尚未完成的下载。升级后版本应显示 1.12.8.2，设置和恢复记录继续保留。

适用于 macOS 13 及以上的 Apple Silicon Mac。应用使用 ad-hoc 签名，尚未经过 Apple 公证。

## English

This maintenance build increments the delivery version only; application behavior is unchanged from 1.12.8.1. Users running 1.12.8.1 can start the update in Settings to verify the button percentage, continued download after closing the interface, silent installation and automatic restart.

Keep Tokki running in the background. Closing its window preserves the download; quitting Tokki stops an unfinished download. After the update, the app should show version 1.12.8.2 with existing settings and recovery records retained.

Requires macOS 13 or later on Apple Silicon. The app is ad-hoc signed and has not been notarized by Apple.

## macOS 1.12.8.1 — 2026-11-08

## 中文

- 更新按钮直接显示下载百分比；关闭设置、弹窗或主窗口后，只要 Tokki 后台仍在运行，下载就会继续。重新打开时显示当前进度。
- 安装包校验通过后自动安装并重启，保留设置和恢复记录。无法安全退出或安装失败时停止，保留原程序并允许重试。
- 本次不改变唤醒与定时行为。

从旧版升级到本版，请下载 DMG 并运行 `Install.command`。安装本版后，后续更新可使用上述自动升级流程。退出 Tokki 后，尚未完成的下载会停止。

适用于 macOS 13 及以上的 Apple Silicon Mac。应用使用 ad-hoc 签名，尚未经过 Apple 公证，系统可能要求允许打开。

## English

- The update button shows download progress as a percentage. Downloads continue after closing Settings, the popover or the main window while Tokki remains running in the background. Reopening the interface shows the current progress.
- Verified packages install automatically and restart Tokki, preserving settings and recovery records. An unsafe exit or installation failure stops the update and keeps the previous application available for retry.
- Wake-up and timer behavior is unchanged.

To upgrade from an older version, download the DMG and run `Install.command`. Once this version is installed, subsequent updates can use the automatic update flow. Quitting Tokki stops unfinished downloads.

Requires macOS 13 or later on Apple Silicon. The app is ad-hoc signed and has not been notarized by Apple; macOS may require permission to open it.

## Windows 1.12.5.2

### 中文

- 延长慢速网络的安装包下载等待时间，下载期间说明正在校验；失败时提示超时、磁盘空间、目录权限或同名文件冲突。
- 下载目录中已有同名且校验通过的安装包时直接显示该文件；校验不符时保留原文件并提示移走。
- Windows 上自然中断后的自动恢复尚未完成端到端实测；用于无人值守任务前请了解这一限制。

### English

- Allow more time for slow installer downloads, show a downloading message, and explain timeout, disk space, permission, or filename conflicts.
- Reuse an existing installer when its SHA-256 matches; keep a conflicting file intact and ask the user to move it.
- Automatic recovery after a natural interruption has not yet completed end-to-end validation on Windows.

## Windows 1.12.5.1

### 中文

- 再次启动 Tokki 时显示已经运行的窗口，仍只保留一个主进程。
- 设置页署名改为可点击的 MossAndMaurice 仓库链接，并调整隐私提示文案。
- Windows 上自然中断后的自动恢复尚未完成端到端实测；用于无人值守任务前请了解这一限制。

### English

- Opening Tokki again now shows the existing window while keeping a single main process.
- The Settings footer links to the MossAndMaurice repository and uses clearer privacy wording.
- Automatic recovery after a natural interruption has not yet completed end-to-end validation on Windows.

## Windows 1.12.5.0

### 中文

- 首个公开 Windows 安装包，支持选择安装目录、托盘运行、查看额度和会话，以及检查同平台的新版本。
- 安装包经过正式构建和安装验收。Windows 上自然中断后的自动恢复尚未完成端到端实测，暂不建议把它作为无人值守任务的唯一保障。

### English

- First public Windows installer with a choice of installation folder, system tray operation, quota and session views, and platform-specific update checks.
- The installer passed the release build and installation checks. Automatic recovery after a natural interruption has not yet completed end-to-end validation on Windows; do not rely on it as the sole safeguard for unattended work.

## macOS 1.12.6.1 — 2026-11-07

### 中文

- 历史发现采用最近五个有更新记录的本地日期，跳过空日期。每轮额外检查最多八条，新建或更新的会话优先。
- 已监控、活动、连接待核验及未结束计划的会话继续保留，包括索引窗口外的监控目标；关闭监控的旧会话仍可重新开启。
- 诊断日志统一时间、进程与会话关联，补齐监控状态变化和读取失败原因。加入容量限制、轮换及只读导出，兼容旧日志格式。
- 诊断导出失败单独处理。升级后继承原有设置、计划和发送记录，首次启动会整理旧诊断日志。

适用于 macOS 13 及以上的 Apple Silicon Mac。打开 DMG，运行 `Install.command` 安装或覆盖升级。

### English

- Historical discovery now uses the five most recent local dates with updates, skipping empty dates. Each refresh checks up to eight additional historical candidates, prioritizing new or updated chats.
- Monitored, active, pending-connection and unfinished-plan chats remain available, including monitored chats outside the recent index. Previously disabled chats remain available for re-enabling.
- Diagnostic logs now share consistent timestamps and process/session correlation, with monitoring transitions and read-failure details. Added bounded retention, rotation and read-only export with legacy-log support.
- Diagnostic export failures are handled separately. Upgrades retain settings, plans and delivery records. The first launch organizes older diagnostic logs.

Requires macOS 13 or later on Apple Silicon. Open the DMG and run `Install.command` to install or upgrade.

## macOS 1.12.4.3 — 2026-11-05

### 中文

- 修复同一台 Mac 上同时运行多个 Tokki 的问题。覆盖升级时，安装器会等待已运行的旧副本安全退出。
- 修复活动会话漏报。一个会话的查询超时时，Tokki 仍可在同一轮确认其他正在运行的 Codex 会话。

适用于 macOS 13 及以上的 Apple Silicon Mac。打开 DMG，运行 `Install.command` 即可安装或覆盖升级。

### English

- Fixed multiple Tokki copies running at the same time on one Mac. During an upgrade, the installer waits for running copies to quit safely.
- Fixed missing active sessions when one Codex session lookup timed out. Tokki can now confirm other active sessions in the same refresh.

Requires macOS 13 or later on Apple Silicon. Open the DMG and run `Install.command` to install or upgrade.

## macOS 1.12.4.2 — 2026-11-05

### 中文

- 修复唤醒已成功、记录仍显示「结果未知」的情况。Tokki 能在后续核对中补记成功，包括重启应用之后。
- 修复取消唤醒计划时，正在进行的额度检查可能让已取消计划重新出现的问题。
- 主窗口和菜单栏弹窗的唤醒卡片显示更完整的核验时间。本地接入与诊断选项移入调试模式，日常使用时默认隐藏。

适用于 macOS 13 及以上的 Apple Silicon Mac。打开 DMG，运行 `Install.command` 即可安装或覆盖升级。

### English

- Fixed wake history showing an unknown result after a session had already resumed. Tokki can confirm the result later, including after an app restart.
- Fixed a quota check that could restore a wake plan after it had been canceled.
- The main window and menu bar popover now show the wake check time more clearly. Local connection and diagnostics settings are hidden by default and available in debug mode.

Requires macOS 13 or later on Apple Silicon. Open the DMG and run `Install.command` to install or upgrade.

## macOS 1.12.2.0 — 2026-11-04

The first public macOS DMG is here. Requires an Apple Silicon Mac running macOS 13 or later.

- Open the DMG and run `Install.command`. The installer requests a safe exit from the old Tokki, preserves settings and recovery records, and starts the installed app.
- The app and mounted disk use the same Tokki puppy icon.
- Opening Settings checks for updates automatically. The update row appears only when a newer version is available, with a “开始更新” button.
- The author name MossAndMaurice opens this GitHub repository.

This build is ad-hoc signed and has not been notarized by Apple. Windows is coming soon. Existing recovery checks and scheduling rules are unchanged; duplicate scheduling remains under investigation. See the README for recovery limitations.

首个公开 macOS DMG 安装包，适用于 macOS 13 及以上的 Apple Silicon Mac。

- 打开 DMG，运行 `Install.command`。升级时请求旧版安全退出，保留设置与恢复记录，并启动安装后的应用。
- 应用与挂载磁盘使用同一只 Tokki 小狗图标。
- 打开设置自动检查更新；只有发现新版才显示更新行和“开始更新”。
- 点击作者名 MossAndMaurice 可打开本 GitHub 仓库。

本包使用 ad-hoc 签名，尚未经过 Apple 公证。Windows 版即将推出。既有恢复核验与定时规则不变，重复定时仍在排查；恢复功能的适用范围和限制见 README。
