<h1 align="center">Tokki</h1>

<p align="center">Let Tokki babysit Codex so you can finally get some sleep.</p>

<p align="center"><strong>English</strong> · <a href="README.zh-CN.md">简体中文</a></p>

<p align="center"><a href="https://github.com/MossAndMaurice/Tokki/releases/tag/macos%2Fv1.12.8.3"><strong>Download for macOS</strong></a> · <a href="https://github.com/MossAndMaurice/Tokki/releases/tag/windows%2Fv1.12.7.2"><strong>Download for Windows</strong></a> · <a href="CHANGELOG.md">Release notes</a></p>

![Raised signs fixed to a solid panel: Seriously?! Stopped AGAIN?! Tokki's got this. I'm going to bed!](assets/tokki-hero-3d-en-v4.png)

You leave Codex working on something. Go to bed. Come back expecting a finished task.

It hit a usage limit shortly after you left. It's been waiting ever since.

**Tokki is for that.** It runs in your Mac’s menu bar, watches the sessions you choose, and sends a follow-up in the original chat when quota is available and the session checks pass. The default message is `继续` (“continue”). Change it in Settings if you like.

One less reason to keep checking on a job you already handed off.

## What it does

- Shows remaining Codex quota and reset times in the menu bar.
- Remembers which monitored sessions were interrupted and checks them individually.
- Can also handle supported connection failures after Codex gives up retrying, and model-capacity errors.
- Checks the original task before sending. An active task, a draft, or pending input blocks the attempt.
- Checks that a new task actually started. If a send result is unclear, it won’t automatically send that attempt again.

It won’t get around a usage limit. There still has to be quota to use.

## Install

**Apple Silicon Mac · macOS 13+**

Requires Codex Desktop and an installed, signed-in Codex CLI. Windows has a separate installer below. Linux is not currently available.

1. Download `Tokki-macOS-….dmg` from the **Assets** section of the [latest macOS release](https://github.com/MossAndMaurice/Tokki/releases/tag/macos%2Fv1.12.8.3).
2. Open the DMG and run **`Install.command`** to install or upgrade.
3. Open Tokki from the menu bar and turn on monitoring for the sessions you want to resume.

Keep Tokki and Codex running. The Mac needs to be awake. Launch at login is available in Settings.

Starting with macOS 1.12.8.1, click **Start update** in Settings when a newer version is available. The button shows the download percentage. Downloads continue after closing the interface while Tokki stays running in the background; verified packages install automatically and restart Tokki. Settings and recovery records are retained. If a safe exit or installation is unavailable, the update stops and can be retried. To move from an older version to this release, run `Install.command` once.

**The current app is ad-hoc signed and has not been notarized by Apple.** macOS may block it from opening. Check the release notes before installing.

### Windows

Download `Tokki-Windows-1.12.7.2.exe` from the [Windows release](https://github.com/MossAndMaurice/Tokki/releases/tag/windows%2Fv1.12.7.2) and run the installer. Choose an installation folder in the wizard, then open Tokki from the system tray. If an older running version asks you to quit, exit Tokki from the tray and select Retry in the installer. Later updates started in Settings download, verify, and install silently. Windows 11 x64 is the initial validation target. Automatic recovery after a natural interruption has not yet completed end-to-end validation on Windows; see the release notes before using it for unattended work.

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
