# Caddx PC Tool

[English](./README.md) | **简体中文**

## 简介

**Caddx PC Tool** 是一款面向消费端用户的图传固件升级工具，用于对 Caddx Ascent 系列图传设备进行固件更新、版本升级和功能维护，并支持 GM 系列云台的固件升级与参数配置。软件可在 Windows、macOS 和 Linux 上运行。

该工具可帮助用户将图传设备升级至最新固件版本，以获得更稳定的图传性能、更好的兼容性以及后续新增功能支持。

---

## 支持设备

本工具适用于以下 Caddx Ascent 系列产品：

- Caddx Ascent Lite
- Caddx Ascent Lite +
- Caddx Ascent VRX 
- Caddx Ascent VRX Pro
- Caddx Ascent GM1 V2
- Caddx Ascent GM3 V2

---

## 主要功能

- **固件升级**：支持拖拽或选择本地固件文件，自动校验固件与设备是否匹配，并实时显示升级进度和结果。
- **云台管理**（GM1 V2 / GM3 V2）：云台固件升级；工作模式、灵敏度、通道、增益、跟随角度等参数配置；参数的载入、保存与烧写；位置校准和陀螺仪校准。
- **设备自动识别**：USB 接入后自动识别设备，连接后显示硬件版本、固件版本、序列号等信息，支持热插拔。
- **多语言**：支持简体中文、English、Русский，可跟随系统语言。
- **日志与技术支持**：一键打开日志文件夹，内置联系客服入口。

---

## 系统要求

| 项目 | 要求 |
| --- | --- |
| 操作系统 | Windows 10 / Windows 11 或更高版本（64 位）<br>macOS 11 或更高版本（Apple Silicon 芯片）<br>Linux x86_64（AppImage / deb） |
| USB 接口 | USB 2.0 或更高版本 |
| 数据线 | 建议使用原装或质量可靠的数据线 |
| 供电 | 升级过程中请确保设备供电稳定 |

---

## 下载

请前往 [Releases](https://github.com/CaddxFPV-Cust/Caddx-PC-Tool-C-Release/releases/latest) 页面下载最新版本，按系统选择对应文件（`<x.y.z>` 为实际版本号）。

| 平台 | 文件 | 说明 |
| --- | --- | --- |
| Windows x64 | `CADDX-PC-Tool-v<x.y.z>-C-Windows-x64-Setup.exe` | 安装版 |
| Windows x64 | `CADDX-PC-Tool-v<x.y.z>-C-Windows-x64-Portable.zip` | 便携版，免安装 |
| macOS（Apple Silicon） | `CADDX-PC-Tool-v<x.y.z>-C-macOS-arm64.dmg` | 安装镜像，打开后将应用拖入「应用程序」文件夹 |
| macOS（Apple Silicon） | `CADDX-PC-Tool-v<x.y.z>-C-macOS-arm64.zip` | 压缩包，解压后将应用拖入「应用程序」文件夹 |
| Linux x86_64 | `CADDX-PC-Tool-v<x.y.z>-C-Linux-x86_64.deb` | 软件包安装，自动配置 udev 规则 |
| Linux x86_64 | `CADDX-PC-Tool-v<x.y.z>-C-Linux-x86_64.AppImage` | 免安装，需手动配置 udev 规则 |

---

## 安装步骤

### Windows

**安装版**

1. 双击下载的 `…-Windows-x64-Setup.exe`。
2. 如出现「Windows 已保护你的电脑」提示，点击「更多信息」，再点击「仍要运行」。
3. 按照安装向导完成安装。

**便携版**

1. 下载 `…-Windows-x64-Portable.zip`，解压到本地目录。
2. 双击 `CADDX PC Tool C.exe` 运行，无需安装。

### macOS

1. 下载 `.dmg` 或 `.zip` 文件：`.dmg` 直接打开，`.zip` 先解压。
2. 将 `CADDX PC Tool C` 拖入「应用程序」文件夹。
3. 首次打开如出现安全提示，选择「打开」。

### Linux

**deb 包（推荐）**

deb 包会自动配置 udev 规则。双击 `.deb` 文件用系统软件安装器安装，或在终端执行下方命令。

```bash
sudo apt install ./CADDX-PC-Tool-v<x.y.z>-C-Linux-x86_64.deb
```

**AppImage**

1. 为文件添加执行权限：`chmod +x CADDX-PC-Tool-v<x.y.z>-C-Linux-x86_64.AppImage`
2. 双击运行，或在终端中直接执行该文件。
3. AppImage 不会配置 udev 规则，请按「注意事项」一节手动配置。

---

## 使用说明

### 固件升级

1. 用 USB 线将设备连接到电脑，然后启动软件。「设备管理」页会自动识别并显示设备。
2. 点击设备卡片上的「连接」，进入固件升级页。
3. 将固件文件拖入升级区域，或点击「选择固件」。
4. 点击「开始升级」，在弹出的「温馨提示」窗口中确认。
5. 等待进度完成。升级期间请保持 USB 连接和设备供电，不要拔插数据线。

### 云台

适用于 GM1 V2 和 GM3 V2 云台。连接云台后，在设备卡片上点击「连接」进入云台页。

- **固件升级**：选择或拖入云台固件文件，点击「开始升级」。
- **参数配置**：设置云台的工作模式、灵敏度、通道、增益和跟随角度。「载入参数」从参数文件读取参数并下发到云台；「保存参数」将当前参数保存为文件；「烧写参数」将当前参数写入云台。
- **校准**：「位置校准」和「校准陀螺仪」。

---

## 注意事项

- 升级过程中请保持 USB 连接和设备供电，不要拔插数据线、关闭软件或给设备断电。
- 升级过程中设备指示灯异常闪烁或自行重启属于正常现象，请耐心等待升级完成。
- 请使用与设备型号匹配的固件文件。软件会校验固件与设备是否匹配，不匹配时不会开始升级。
- 不建议对设备进行降级操作。
- 使用前请阅读软件内的用户协议（「软件设置」→「用户协议」）。
- **Linux**：Ubuntu 等默认启用 ModemManager 的发行版，需要配置本工具的 udev 规则，否则系统服务可能占用设备串口，导致升级失败。deb 包会自动配置；AppImage 请手动执行下方命令，配置后重新插拔一次设备。

```bash
./CADDX-PC-Tool-v<x.y.z>-C-Linux-x86_64.AppImage --appimage-extract
sudo cp squashfs-root/udev/60-caddx-pc-tool.rules /etc/udev/rules.d/
sudo udevadm control --reload-rules
```

---

## 常见问题

**Windows 提示「Windows 已保护你的电脑」**

安装包未做代码签名，Windows SmartScreen 会弹出此提示。点击「更多信息」，再点击「仍要运行」即可。

**设备显示「未识别设备」或「未识别设备A」**

请确认设备型号在「支持设备」列表内，然后重新插拔 USB；仍无法识别时，更换数据线或 USB 接口后重试。

**提示「软件已在运行」**

Caddx PC Tool 同一时间只能运行一个实例，请先关闭已打开的软件窗口。

**升级失败或设备无响应**

重新插拔设备 USB，检查数据线和供电后重试。若问题依旧，请联系技术支持，并提供软件版本号和日志文件。

**Linux AppImage 无法启动，提示找不到 libfuse.so.2**

安装 FUSE 2 运行库后重试（Ubuntu 22.04：`sudo apt install libfuse2`；Ubuntu 24.04：`sudo apt install libfuse2t64`），或启动时加上 `--appimage-extract-and-run` 参数。

---

## 技术支持

- 邮箱：support@caddxfpv.com
- 官网：https://www.caddxfpv.com
- 软件内「帮助中心 → 联系客服」提供更多联系方式。

反馈问题时，请附上软件版本号（显示在软件左下角）和日志文件（「软件设置」→「打开日志文件夹」）。
