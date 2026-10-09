# Codex Link Engine（PC 端）

**Codex Link** —— 手表 Wi-Fi 遥控 PC Codex 编程。

手表通过局域网（TCP）向 PC 端发送控制指令，PC 端将指令转换为键鼠操作，发送给处于前台的 Codex 桌面应用或 CLI，实现远程控制；同时 PC 端会把 Codex 的运行状态（任务开始 / 完成、token 用量等）实时回传到手表端展示。

> 本仓库发布 **PC 端可执行文件（exe）** 与各手表端**测试安装包**，源代码暂不公开。

## 应用展示

| HarmonyOS 手表端 | Wear OS 手表端 |
|:---:|:---:|
| ![HarmonyOS 手表端](./screenshot-harmonyos.jpeg) | ![Wear OS 手表端](./screenshot-wearos.png) |

## 各端版本

| 端 | 技术栈 | 说明 |
| --- | --- | --- |
| **PC 端 Codex Link Engine** | C# .NET 8 WinForms | 本仓库发布（免费） |
| **HarmonyOS 手表端 Codex Link Watch** | DevEco Studio / ArkTS | 华为 WATCH 5 系列等；**已上架华为应用市场**（覆盖中国大陆，不含香港、澳门、台湾），**免费下载** |
| **Wear OS 手表端 Codex Link Wear** | Android Studio / Kotlin + Compose for Wear OS | 面向 Wear OS / Android 手表（三星、Pixel Watch 等），提供连接配对、快捷命令、Agent 键、项目进度与状态心跳等能力，与 HarmonyOS 版功能持续对齐 |
| **手机端 Codex Link Phone**（MVP） | DevEco Studio / ArkTS | HarmonyOS 手机，连接 + Agent/Command 键 + 状态灯 + 设置 |

> **关于开源**：所有端（含 Wear OS 版）的源代码均**暂不公开**。本仓库提供 PC 端可执行文件与手表端测试安装包；正式版本与一键配置包可通过下方 QQ 群获取。

## 使用手册

完整使用说明见 **[使用手册.md](./使用手册.md)**（系统组成、启动准备、PC 端操作、手表端操作、按键映射、端口协议、常见问题等）。

## 下载

| 文件 | 说明 |
| --- | --- |
| [CodexLinkEngine-1.2.5.zip](./CodexLinkEngine-1.2.5.zip) | PC 端主程序 Codex Link Engine **v1.2.5**（Windows 10 / 11 x64，单文件版） |
| [codex-status-hook.zip](./codex-status-hook.zip) | Codex 状态钩子，把 Codex hooks 事件转发给引擎 |
| [CodexLinkWear-wearos-v1.0-test.apk](./CodexLinkWear-wearos-v1.0-test.apk) | **Wear OS 手表端测试版 v1.0**（.apk，调试构建、未混淆、体积偏大） |
| [CodexLinkWatch-harmonyos-v1.3.8-test.hap](./CodexLinkWatch-harmonyos-v1.3.8-test.hap) | **HarmonyOS 手表端测试版 v1.3.8**（.hap，签名直装包） |

### 手表端测试包安装

- **Wear OS（.apk）**：在手表上开启「开发者选项 → ADB 调试」并允许通过 Wi-Fi 调试，在电脑上执行 `adb install CodexLinkWear-wearos-v1.0-test.apk` 完成安装；首次使用在手表端填入 PC 的局域网 IP 并与引擎配对。
- **HarmonyOS（.hap）**：正式版**已上架华为应用市场**（覆盖中国大陆地区，暂不含香港、澳门、台湾），**免费**下载安装；如需侧载测试，可通过 DevEco Studio 安装或执行 `hdc install CodexLinkWatch-harmonyos-v1.3.8-test.hap`。

## Downloads (English)

**Codex Link** lets you control AI coding sessions running on your Windows PC from a smartwatch over local Wi-Fi. The watch sends control commands to the PC-side engine (TCP 9527), which translates them into keyboard/mouse actions for the Codex desktop app or CLI, while task status (start / completion, token usage) is streamed back to the watch in real time.

| File | Description |
| --- | --- |
| [CodexLinkEngine-1.2.5.zip](./CodexLinkEngine-1.2.5.zip) | PC-side engine, Codex Link Engine **v1.2.5** for Windows 10 / 11 x64 (single-file build) |
| [codex-status-hook.zip](./codex-status-hook.zip) | Codex status hook — forwards Codex hooks events to the engine |
| [CodexLinkWear-wearos-v1.0-test.apk](./CodexLinkWear-wearos-v1.0-test.apk) | **Wear OS watch client, test build v1.0** (.apk; debug build, not obfuscated, larger size) |
| [CodexLinkWatch-harmonyos-v1.3.8-test.hap](./CodexLinkWatch-harmonyos-v1.3.8-test.hap) | **HarmonyOS watch client, test build v1.3.8** (.hap; signed package for direct installation) |

**Installing the Wear OS test build (.apk):** enable Developer options → ADB debugging on the watch and allow Wi-Fi debugging, then run `adb install CodexLinkWear-wearos-v1.0-test.apk` from your PC. On first launch, enter the PC's LAN IP in the watch app and pair it with the engine.

**Installing the HarmonyOS test build (.hap):** the official release is **now available on HUAWEI AppGallery** (mainland China, excluding Hong Kong, Macau and Taiwan), free of charge; for sideloading tests, install the signed `.hap` from DevEco Studio or run `hdc install CodexLinkWatch-harmonyos-v1.3.8-test.hap`.

**Requirements:** a Windows 10/11 PC running CodexLinkEngine, and the watch and PC connected to the same Wi-Fi network with client (AP) isolation disabled. Both the PC engine and the HarmonyOS watch app (now on HUAWEI AppGallery) are free.

## 系统要求

- Windows 10 / 11 桌面端（x64）
- 本机已安装 Codex 桌面应用或 CLI，可正常启动会话
- PC 与手表连接同一个 Wi-Fi（路由器需允许客户端互通，禁用「AP 隔离」）

## 快速开始

1. 解压并运行 `CodexLinkEngine.exe`。
2. 首次运行时，Windows 防火墙弹窗请勾选「专用网络」并允许（或手动放行 TCP 9527、UDP 9528）。
3. 按引擎内使用手册的步骤，与手表端配对连接。
4. 手表端通过 Wi-Fi 连接后，即可遥控 PC 端 Codex 并查看实时状态。

## 端口与协议

- TCP 9527：手表 → PC 控制指令
- UDP 9528：局域网设备发现（配对信标）

## 隐私说明

- 所有数据仅存储于本机，不上传至任何服务器。
- 配对码与连接信息仅保存在本地，用于自动重连。
- 状态回传仅包含任务进度信息，不包含对话内容本身。

## 相关说明

- HarmonyOS 手表端**已上架华为应用市场**（覆盖中国大陆，不含香港、澳门、台湾），**免费**；PC 端 Codex Link Engine 免费。
- 适用设备：华为 WATCH 5 系列等 HarmonyOS 手表，以及支持 Wear OS / Android 应用的手表；具体厂商型号需单独验证。
- 当前版本仅支持 Windows，macOS / Linux 等平台后续版本将逐步适配。

## 联系与反馈

- 官方 QQ 群：**596473771**（获取最新版本 / 一键配置包 / 反馈问题）
- 邮箱：Lx31046@outlook.com

扫码进群：

![QQ 群二维码](./qrcode.png)
