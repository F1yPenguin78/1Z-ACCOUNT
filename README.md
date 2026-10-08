# Account · 本地记账 · Offline Ledger

**免费、完全离线的 Android 记账 App — 数据只存在你自己的手机上。**
**A free, fully offline expense tracker for Android — your data never leaves your device.**

[简体中文](#-简体中文) · [English](#-english) · [版本信息 / Release Info](#版本信息--release-info)

![platform](https://img.shields.io/badge/Platform-Android-3DDC84?logo=android&logoColor=white)
![minSdk](https://img.shields.io/badge/minSdk-24%20%2F%20Android%207.0-blue)
![targetSdk](https://img.shields.io/badge/targetSdk-37%20%2F%20Android%2017-blue)
![version](https://img.shields.io/badge/version-1.0-brightgreen)
![network](https://img.shields.io/badge/network-none-critical)

---

## 🇨🇳 简体中文

### 这是什么

**Account** 是一款免费的 Android 记账软件，主打**纯本地、完全离线**。

它没有账号系统，不需要注册和登录，也不申请任何网络权限——App 从物理上就无法联网。你的每一笔收支都写在本机的数据库里，不会上传到任何服务器，没有广告，没有数据分析 SDK，也没有内购。

界面语言为简体中文（本说明文档提供中英双语）。

### 下载安装

| | |
|---|---|
| 下载地址 | **[Account.apk](https://github.com/F1yPenguin78/1Z-ACCOUNT/raw/main/Account.apk)** |
| 文件大小 | 4.92 MB（5,156,115 字节） |
| 版本 | 1.0（versionCode 1） |
| 包名 | `com.ds.account` |
| SHA-256 | `A76B7510751F8A4B072379CB67EDA57221D6AAE1D9316424DCAFACCD93B95862` |

安装步骤：

1. 手机浏览器打开上面的下载链接（或用数据线把 `Account.apk` 拷进手机）
2. 点击 APK 安装；系统若提示「禁止安装未知应用」，在弹窗里允许当前来源安装即可
3. 装好后直接打开就能用，无需任何权限授予

### 功能一览

**记一笔** — 记录支出或收入，可选择分类、日期，填写金额和备注（备注可不填）。

**明细** — 按月查看所有记录，支持切换月份、修改某一笔、删除某一笔（删除前会二次确认）。当月没有记录时会给出引导提示。

**统计** — 汇总本月支出、本月收入、本月结余（若为负数则显示为「超支」），并按分类展示本月支出构成。

**总金额库** — App 顶部的核心数字，代表你当前手上的总金额。长按即可手动修正，并可以填写修正原因。

**额外收支** — 有些钱不属于当月日常开销（比如临时报销、一次性大额支出）。这类可以单独录入为「额外收入 / 额外支出」，它会直接增减总金额库，但**不**计入当月的收支统计，避免污染月度数据。

**每月自动结算** — 每月 1 日 00:01，App 会自动把上个月的结余或超支计入总金额库，无需手动操作。App 内会显示下一次自动结算的时间。

**CSV 导入 / 导出** — 可以把记录导出成 `account-export.csv`，也可以从 CSV 导入。导入采用**追加**方式，绝不覆盖你已有的数据；导入结束后会告诉你成功多少条、跳过多少条。

### 隐私说明

这款 App 的隐私模型非常简单粗暴：**它拿不到网络，所以传不出去。**

- manifest 中没有声明 `android.permission.INTERNET`
- 数据存放在本机应用的私有目录（Room / SQLite 数据库）
- 无账号、无登录、无云端同步、无广告、无第三方统计

> App 内的「关于」页面原话：*Account · 本地记账 —— 数据只保存在这台设备上，App 不含任何联网权限。*

### 权限说明

App 只声明了 4 个系统权限，全部与记账本身相关：

| 权限 | 用途 |
|---|---|
| `WAKE_LOCK` | 执行后台结算任务时保持 CPU 唤醒，避免算到一半被打断 |
| `ACCESS_NETWORK_STATE` | 仅读取网络连接状态（**不代表可以联网**，无法收发数据） |
| `RECEIVE_BOOT_COMPLETED` | 开机后重新注册每月的自动结算任务 |
| `FOREGROUND_SERVICE` | 结算任务较长时以前台服务方式运行，保证完成 |

> 注意：`ACCESS_NETWORK_STATE` 只能查询「当前是否有网络」，它**不授予**任何访问网络的能力。

### 兼容性

- **最低支持 Android 7.0（API 24）**
- **目标版本 Android 17（API 37），并已验证可在 Android 17 上正常运行**

### 关于本仓库

本仓库用于分发编译好的 APK，**不包含源码**。软件完全免费使用。

---

## 🇬🇧 English

### What is this

**Account** is a free Android expense tracker built around one idea: **stays on your device, works with no network at all.**

There is no account system, no sign-up, no login — and no network permission whatsoever. The app is physically incapable of going online. Every entry you record is written to a local database on your phone: nothing is uploaded, there are no ads, no analytics SDKs, and no in-app purchases.

The app's user interface is in **Simplified Chinese**. This README is bilingual.

### Download & install

| | |
|---|---|
| Download | **[Account.apk](https://github.com/F1yPenguin78/1Z-ACCOUNT/raw/main/Account.apk)** |
| File size | 4.92 MB (5,156,115 bytes) |
| Version | 1.0 (versionCode 1) |
| Package | `com.ds.account` |
| SHA-256 | `A76B7510751F8A4B072379CB67EDA57221D6AAE1D9316424DCAFACCD93B95862` |

Steps:

1. Open the download link on your phone (or copy `Account.apk` over with a USB cable)
2. Tap the APK to install; if Android blocks it, allow installing from that source when prompted
3. Launch it — there is nothing to configure and no permissions to grant

### Features

**Record an entry** — Log an expense or an income, pick a category and date, enter the amount and an optional note.

**Details** — Browse every entry by month, switch months, edit an entry, or delete one (with a confirmation prompt). An empty month shows a friendly hint instead of a blank screen.

**Statistics** — Monthly totals for expenses, income and net balance (shown as "overspent" when negative), plus a breakdown of the month's spending by category.

**Total balance pool** — The headline number at the top of the app: how much money you actually have. Long-press it to correct the value by hand, optionally recording a reason for the adjustment.

**Extra income / expense** — For money that isn't part of this month's day-to-day spending (a reimbursement, a one-off large payment), record it as an *extra* item. It adjusts the total balance pool directly and is deliberately **excluded** from the monthly income/expense statistics.

**Automatic monthly settlement** — At 00:01 on the 1st of every month, the app automatically rolls the previous month's surplus or overspend into the total balance pool. No manual step, and the app shows you when the next settlement will run.

**CSV import / export** — Export your records to `account-export.csv`, and import them back. Importing **appends** — it never overwrites existing data — and reports how many rows were imported and how many were skipped.

### Privacy

The privacy model is refreshingly blunt: **it has no network access, so it cannot leak anything.**

- No `android.permission.INTERNET` declared in the manifest
- Data lives in the app's private storage on your device (Room / SQLite database)
- No account, no login, no cloud sync, no ads, no third-party analytics

> Quoting the app's own About screen: *"Account · 本地记账 — Data is kept only on this device; the app holds no network permission."*

### Permissions

The app declares just four system permissions, all in service of bookkeeping itself:

| Permission | Why |
|---|---|
| `WAKE_LOCK` | Keeps the CPU awake while the background settlement job runs, so it isn't cut off halfway |
| `ACCESS_NETWORK_STATE` | Reads connectivity status only — it **does not** grant any ability to send or receive data |
| `RECEIVE_BOOT_COMPLETED` | Re-registers the monthly settlement job after a reboot |
| `FOREGROUND_SERVICE` | Runs a long settlement as a foreground service so it can finish reliably |

> Note: `ACCESS_NETWORK_STATE` only answers "is there a network right now". It grants **no** network capability.

### Compatibility

- **Requires Android 7.0 (API 24) or newer**
- **Targets Android 17 (API 37), and has been verified to run correctly on Android 17**

### About this repository

This repository distributes the compiled APK only — it does **not** contain the source code. The software is completely free to use.

---

## 版本信息 / Release Info

| | |
|---|---|
| 应用名 / App name | Account |
| 包名 / Package | `com.ds.account` |
| 版本 / Version | 1.0 (versionCode 1) |
| 最低系统 / Min SDK | API 24 — Android 7.0 |
| 目标系统 / Target SDK | API 37 — Android 17 |
| 编译 SDK / Compile SDK | API 37 — Android 17 |
| 文件 / File | `Account.apk` — 5,156,115 bytes (4.92 MB) |
| SHA-256 | `A76B7510751F8A4B072379CB67EDA57221D6AAE1D9316424DCAFACCD93B95862` |

## 反馈 / Feedback

遇到问题或有建议，欢迎在 [Issues](https://github.com/F1yPenguin78/1Z-ACCOUNT/issues) 里提出。
Found a bug or have a suggestion? Please open an [issue](https://github.com/F1yPenguin78/1Z-ACCOUNT/issues).
