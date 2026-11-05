# Release notes · 更新日志

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
