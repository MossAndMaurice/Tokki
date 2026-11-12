<h1 align="center">Tokki · Automatic Codex Resume</h1>

<p align="center">Resume interrupted Codex tasks automatically when quota returns.</p>

<p align="center"><strong>English</strong> · <a href="README.zh-CN.md">简体中文</a></p>

<p align="center"><a href="https://github.com/MossAndMaurice/Tokki/releases/tag/macos%2Fv1.13.0.0"><strong>Download for macOS</strong></a> · <a href="https://github.com/MossAndMaurice/Tokki/releases/tag/windows%2Fv1.14.0.0"><strong>Download for Windows</strong></a> · <a href="CHANGELOG.md">Release notes</a></p>

![Raised signs fixed to a solid panel: Seriously?! Stopped AGAIN?! Tokki's got this. I'm going to bed!](assets/tokki-hero-3d-en-v4.png)

You leave Codex working on something. Go to bed. Come back expecting a finished task.

It hit a usage limit shortly after you left. It's been waiting ever since.

**Tokki resumes Codex automatically.** It runs in your Mac’s menu bar, watches the sessions you choose, and sends a follow-up in the original chat when quota is available and the session checks pass. The default message is `继续` (“continue”). Change it in Settings if you like.

One less reason to keep checking on a job you already handed off.

## What it does

- Automatically resumes monitored Codex tasks in the original chat when quota returns and session checks pass.
- Shows remaining Codex quota and reset times in the menu bar.
- Remembers which monitored sessions were interrupted and checks them individually.
- Can also handle supported connection failures after Codex gives up retrying, and model-capacity errors.
- Checks the original task before sending. An active task, a draft, or pending input blocks the attempt.
- Checks that a new task actually started. If a send result is unclear, it won’t automatically send that attempt again.

It won’t get around a usage limit. There still has to be quota to use.

## Install

**Apple Silicon Mac · macOS 13+**

Requires Codex Desktop and an installed, signed-in Codex CLI. Windows has a separate installer below. Linux is not currently available.

1. Download `Tokki-macOS-….dmg` from the **Assets** section of the [latest macOS release](https://github.com/MossAndMaurice/Tokki/releases/tag/macos%2Fv1.13.0.0).
2. Open the DMG and run **`Install.command`** to install or upgrade.
3. Open Tokki from the menu bar and turn on monitoring for the sessions you want to resume.

Keep Tokki and Codex running. The Mac needs to be awake. Launch at login is available in Settings.

Starting with macOS 1.12.8.1, click **开始更新 / Update now** in Settings when a newer version is available. The button shows the download percentage. Downloads continue after closing the interface while Tokki stays running in the background; verified packages install automatically and restart Tokki. Settings and recovery records are retained. If a safe exit or installation is unavailable, the update stops and can be retried. For versions older than macOS 1.12.8.1, run `Install.command` once to upgrade.

macOS 1.13.0.0 adds **Language** in Settings: **Follow System**, **简体中文**, and **English**. Tokki checks for updates in the background every 24 hours after a successful check, retaining the check history across restarts. New-version dots guide you from the menu bar and Settings button to the update entry. Viewing the update section clears the outer unread dots; your saved wake message stays unchanged.

**The current app is ad-hoc signed and has not been notarized by Apple.** macOS may block it from opening. Check the release notes before installing.

### Windows

Windows 1.14.0.0 recognizes API keys and verified custom Responses providers. Supported terminal API connection and encrypted-content failures use a bounded recovery chain of up to three attempts. Real gateway recovery still requires target-environment validation.

Download `Tokki-Windows-1.14.0.0.exe` from the [Windows release](https://github.com/MossAndMaurice/Tokki/releases/tag/windows%2Fv1.14.0.0) and run the installer. Choose an installation folder in the wizard, then open Tokki from the system tray. If an older running version asks you to quit, exit Tokki from the tray and select Retry in the installer. Updates started in Settings download and verify the installer, then attempt a silent upgrade; an incomplete older installation may require manual repair. The Diagnostics section in Settings now shows recent local logs and can open the log folder. A Codex desktop session that supplies a verified running snapshot but does not accept external input appears as read-only activity; it cannot authorize automatic wake. Windows 11 x64 is the initial validation target. Automatic recovery after a natural interruption has not yet completed end-to-end validation on Windows; see the release notes before using it for unattended work.

<details>
<summary>A few things to know</summary>

Tokki stores its settings and recovery records locally. It doesn’t rewrite Codex configuration, databases, or session logs. Quota queries and follow-up messages go through Codex.

Recovery requires a recognized interruption and fresh checks of quota, the original session, and the original task. Silence alone doesn’t trigger it. Each recovery plan gets one send attempt, recorded before submission; an uncertain result is never automatically retried.

Quitting Tokki stops its timers. It won’t wake a sleeping Mac or launch a closed Codex. It checks conditions again after reopening or waking. Codex updates may affect compatibility.

Real quota recovery has been confirmed in two original desktop sessions. Account switching, sleep, restarts, and natural network failures haven’t all been verified end to end. Duplicate scheduling is still an open issue. Each release’s notes describe its validation and limitations.

</details>

## Something went wrong?

[Open an issue](https://github.com/MossAndMaurice/Tokki/issues) with the Tokki, macOS, and Codex versions, plus what happened. Please remove credentials and private conversations from screenshots or logs.

This repository is for downloads and release notes. The app’s source code isn’t published here.

## Privacy

**We don’t collect or upload your data.** Your conversations, code, credentials, quota information, and local activity records are not sent to us. Tokki keeps its settings and recovery records on your device, with no usage analytics or telemetry.

Quota queries and wake-up messages go through Codex, whose own network behavior and privacy terms still apply. When an update repository is configured, Tokki checks its public releases on GitHub and sends the Tokki version in the request; it does not include your conversations, code, credentials, or recovery records.

## Copyright & usage

**© 2026 Tokki. All rights reserved.**

Tokki is proprietary software, distributed as compiled releases. You may download, install, and use the official releases. Other rights are reserved, subject to applicable law and the licenses of third-party components. Publishing downloads here does not grant an open-source license to Tokki’s code.

<sub>Tokki is an independent project, not affiliated with or endorsed by OpenAI.</sub>
