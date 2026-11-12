# Release notes · 更新日志

## Windows 1.14.0.0 — 2026-11-12

### 中文

- 支持识别 API Key 和经配置核验的自定义 Responses 接入；界面显示“API 接入”，订阅额度显示不适用。
- 对指定的终结性连接失败和加密校验错误，重新核验原任务后按 5、15、30 秒尝试恢复，连续最多三次；前次启动确认后才接续，结果未知时停止自动恢复。
- 保留 ChatGPT 现有额度与恢复门槛。API 账户切换时清理旧展示，并在发送前重新核对接入模式。
- 508 项源码回归通过。Windows 真实网关自然故障和安装版完整恢复闭环仍待目标环境实测。

### English

- Recognizes API keys and verified custom Responses providers, with an API access label and no subscription quota display.
- Rechecks the original task before recovering supported terminal connection and encrypted-content errors. Recovery uses 5, 15, and 30 second delays, with at most three linked attempts and confirmed starts between attempts. Unknown results stop automatic recovery.
- Preserves existing ChatGPT quota and recovery checks, clears account display caches on mode changes, and verifies the access mode again before sending.
- All 508 source regression tests passed. Natural gateway failures and the complete installed Windows recovery flow still require validation in the target environment.

## Windows 1.13.0.3 — 2026-11-11

### English

- Fixed the Windows install-exit handshake by passing the request ID through Electron's additional data channel. The isolated two-instance test confirmed a safe exit and ready marker.
- Installer failures now write redacted codes to local Diagnostics. If an existing installation is incomplete, the log records which of its app directory, Start Menu shortcut, and registration are present.
- Diagnostics and Local Data is collapsed by default in Settings. The expanded view groups log actions, local data status, and recent entries.
- An already running 1.13.0.2 cannot receive the new handshake; exit it from the tray before this one-time upgrade. Codex Desktop API-account connection failures remain under investigation.

### 中文

- 安装退出请求改用 Electron 的附加数据通道传递；隔离双实例测试已确认安全退出并写出 `ready` 标记。
- 安装失败现在会把脱敏错误码写入本地诊断日志；旧安装不完整时记录程序目录、开始菜单快捷方式和注册项是否存在。
- 设置中的“诊断与本地数据”默认收起；展开后将日志操作、本地数据状态和近期记录分组排列。
- 正在运行的 1.13.0.2 无法接收新版握手；首次升级前请从托盘退出。Codex 桌面 API 账号连接失败仍在排查。
## Windows 1.13.0.2 — 2026-11-11

### English

- The update button shows download percentages, including 0% when starting; cached installers show verification before installation.
- If the previous installation only lost its Start Menu shortcut, the installer verifies ownership, rebuilds the shortcut, and upgrades transactionally.
- Codex Desktop API-account activity with `rejected` or `noOwner` connection failures still needs evidence from the affected PC; this release does not loosen session or send checks.

### 中文

- 更新按钮显示下载百分比，开始时显示 0%；复用已下载的安装包时会先显示校验状态。
- 若旧安装仅丢失开始菜单快捷方式，安装器会核验归属、重建快捷方式并以事务方式升级。
- API 账号的 Codex 桌面会话出现 `rejected` 或 `noOwner` 时，仍需故障机器的证据；本版不放宽会话或发送核验。
## Windows 1.13.0.1 — 2026-11-10

### English

- Settings now shows recent local diagnostic logs, the session-index status, and a button to open the log folder. The misplaced automatic-send explanation was removed from this section.
- When Codex Desktop supplies a verified running snapshot but its session owner does not accept external input, Tokki shows read-only activity. This view does not enable monitoring or authorize automatic wake.
- Discovery and desktop-connection failures now record limited diagnostic codes. API Key account compatibility still requires validation on the affected Windows installation.

### 中文

- 设置页现可查看近期本地诊断日志、会话索引状态，并打开日志文件夹；移除了误放在诊断区的自动发送说明。
- Codex 桌面会话若提供经核验的运行中快照，但 owner 不接受外部输入，Tokki 会显示“只读活动”；该显示不启用监控，也不授权自动唤醒。
- 会话发现和桌面连接失败会记录有限的诊断错误码。API Key 账号的兼容性仍需在出现问题的 Windows 机器上验收。


## macOS 1.13.0.0 — 2026-11-09

## English

- Added **Language** in Settings: **Follow System**, **简体中文**, and **English**. The interface switches immediately; saved wake messages, drafts, and session titles keep their original content.
- Tokki now checks for updates in the background every 24 hours after a successful check. Check history survives restarts, and failed checks retry automatically. Opening Settings no longer forces another check.
- New-version dots appear on the menu-bar icon, Settings button, and update entry. Viewing the update section clears the outer unread dots; the update entry keeps its dot until an update starts. A newer release lights the unread dots again.
- Existing monitoring, recovery, wake-message and safe-installation behavior is retained. Download progress remains available after closing and reopening the interface.

If you already use macOS 1.12.8.1 or later, open Settings and select **开始更新 / Update now** to upgrade. Keep Tokki running in the background while it downloads; a verified update installs automatically and restarts the app. Otherwise, download the DMG and run `Install.command`.

**Apple Silicon Mac · macOS 13 or later.** This app is ad-hoc signed and has not been notarized by Apple. This release is for macOS; Windows installers remain separate.

## 中文

- 设置新增**语言**选项，支持**跟随系统、简体中文、English**，切换立即生效；已保存的唤醒消息、未保存草稿和会话标题保留原文。
- 更新检查改为后台运行：成功检查后每 24 小时检查一次，检查记录跨重启保存，失败时自动退避重试。打开设置不再强制检查。
- 状态栏图标、设置按钮和新版本入口增加红点。查看更新区域后，外层未读红点消失；更新入口的红点保留到开始更新，更高版本会重新提醒。
- 监控、恢复、实际唤醒消息和安全安装规则保持原有行为；关闭再打开界面仍能看到当前下载进度。

已安装 macOS 1.12.8.1 或更高版本的用户，可打开设置，点击**开始更新 / Update now**升级。下载期间请保留 Tokki 后台进程，校验后自动安装并重启。更早版本请下载 DMG，运行 `Install.command`。

**适用于 Apple Silicon Mac，macOS 13 及以上。** 应用使用 ad-hoc 签名，尚未经过 Apple 公证。本次发布为 macOS 版，Windows 继续使用独立安装包。

## Windows 1.12.7.2 — 2026-11-09

### 中文

- 从不支持安全退出的旧版升级时，安装器会明确提示从系统托盘退出 Tokki，并允许直接点击“重试”；旧安装在失败时保留。
- 安装本版后，在设置中点击“开始更新”会下载并校验新版安装包，再静默安装并启动新版。退出前仍须完成既有的发送结果确认，不会强制结束 Tokki。
- 本版保留 MossAndMaurice 可点击署名和新版隐私文案。已安装的旧版本在完成升级前仍显示旧文案。

Windows 11 x64 是首轮验证目标。从本版到未来版本的真实自动安装尚未完成端到端验收；自然中断后的自动恢复也尚未完成完整实机验收。

### English

- When upgrading from an older version without safe exit support, the installer explains how to quit Tokki from the tray and offers Retry. A failed installation preserves the previous app.
- After this version is installed, Start Update in Settings downloads and verifies a newer installer, then runs it silently and starts the new app. The existing send-result confirmation gate still applies before exit; Tokki is never force-terminated.
- The clickable MossAndMaurice credit and updated privacy text remain. An already installed older version keeps its old text until upgraded.

Windows 11 x64 is the initial validation target. A real end-to-end automatic install from this version to a future version has not yet been validated. Automatic recovery after a natural interruption also remains pending full end-to-end validation.

## Windows 1.12.7.1 — 2026-11-09

### 中文

- 暂停、取消计划或关闭会话监控时，立即阻止尚未提交的恢复消息继续发送；新会话也能获得轮转核验机会。
- 退出和升级会等待已提交的发送尝试得到确认或按既有规则转为未知；无法安全退出时，安装会停止并保留正在运行的旧程序。
- 已归档会话恢复后可手动重新核验并开启监控；历史记录较长时给出截断提示，避免误报保存失败。
- 设置中的登录启动状态会读取 Windows 系统的禁用状态，反映任务管理器中的更改。

Windows 11 x64 是首轮验证目标。自然中断后的自动恢复尚未完成完整实机验收；用于无人值守任务前请留意这一限制。

### English

- Pausing, canceling a plan, or disabling session monitoring now stops an unsent recovery message; new sessions also receive rotating verification opportunities.
- Quit and upgrade wait for an in-flight send to be confirmed or classified as unknown under the existing rule. If a safe exit cannot complete, installation stops and leaves the running app in place.
- An archived session can be checked and monitored again after restoration. Long histories show a truncation notice instead of incorrectly reporting a save failure.
- Launch-at-login status reflects a startup item disabled through Windows Task Manager.

Windows 11 x64 is the initial validation target. Automatic recovery after a natural interruption has not yet completed full end-to-end validation.

## macOS 1.12.8.3 — 2026-11-09

## 中文

- 设置页拆成“常规”和“唤醒消息”两张同级卡片，分组更清楚。
- 移除消息输入框下方的说明文字，收紧卡片高度；保留多行输入空间，操作按钮靠右排列。
- 保留现有开关、保存、恢复默认和输入校验；自动更新、唤醒与定时行为不变。

已运行 1.12.8.1 或 1.12.8.2 的用户，可重新打开设置，通过“开始更新”升级到本版。下载时按钮显示百分比；关闭窗口后请保留 Tokki 后台进程，校验完成后自动安装并重启。

适用于 macOS 13 及以上的 Apple Silicon Mac。应用使用 ad-hoc 签名，尚未经过 Apple 公证。

## English

- Settings now has two peer sections: General and Wake Message.
- Removed the helper sentence below the message field and reduced the card height, retaining multiline input and right-aligned action buttons.
- Existing switches, save/reset actions and validation are retained. Update, wake-up and timer behavior is unchanged.

Users running 1.12.8.1 or 1.12.8.2 can reopen Settings and start the in-app update. The button shows download progress. Keep Tokki running in the background after closing the window; a verified package installs automatically and restarts the app.

Requires macOS 13 or later on Apple Silicon. The app is ad-hoc signed and has not been notarized by Apple.

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
