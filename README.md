# Caddx PC Tool

**English** | [简体中文](./README_ZH.md)

## Introduction

**Caddx PC Tool** is a consumer-facing firmware upgrade tool for Caddx Ascent series video transmission devices. It is used to update firmware, upgrade versions, and maintain supported Caddx Ascent series video transmission products. It also updates firmware and configures parameters for GM series gimbals. The app runs on Windows, macOS, and Linux.

This tool helps users upgrade their video transmission devices to the latest firmware version, providing more stable video transmission performance, better compatibility, and support for future features.

---

## Supported Devices

This tool is applicable to the following Caddx Ascent series products:

- Caddx Ascent Lite
- Caddx Ascent Lite +
- Caddx Ascent VRX 
- Caddx Ascent VRX Pro
- Caddx Ascent GM1 V2
- Caddx Ascent GM3 V2

---

## Features

- **Firmware upgrade**: drag and drop or browse for a local firmware file. The tool checks that the firmware matches the connected device and shows upgrade progress and results in real time.
- **Gimbal management** (GM1 V2 / GM3 V2): gimbal firmware upgrade; parameter configuration including mode, sensitivity, channels, gain, and follow angles; load, save, and write parameters; position calibration and gyro calibration.
- **Automatic device detection**: devices are detected as soon as they are connected over USB. Hardware version, firmware version, and serial number are shown once connected. Hot-plugging is supported.
- **Multiple languages**: Simplified Chinese, English, and Russian, with an option to follow the system language.
- **Logs and support**: one-click access to the log folder, plus a built-in customer service page.

---

## System Requirements

| Item | Requirement |
| --- | --- |
| Operating system | Windows 10 / Windows 11 or later (64-bit)<br>macOS 11 or later (Apple Silicon)<br>Linux x86_64 (AppImage / deb) |
| USB port | USB 2.0 or higher |
| USB cable | An original or high-quality USB cable is recommended |
| Power | Ensure stable power supply for the device during the upgrade |

---

## Download

Download the latest version from the [Releases](https://github.com/CaddxFPV-Cust/Caddx-PC-Tool-C-Release/releases/latest) page and pick the file for your operating system (`<x.y.z>` in the file names below is the actual version number).

| Platform | File | Notes |
| --- | --- | --- |
| Windows x64 | `CADDX-PC-Tool-v<x.y.z>-C-Windows-x64-Setup.exe` | Installer |
| Windows x64 | `CADDX-PC-Tool-v<x.y.z>-C-Windows-x64-Portable.zip` | Portable, no installation needed |
| macOS (Apple Silicon) | `CADDX-PC-Tool-v<x.y.z>-C-macOS-arm64.dmg` | Disk image: open it and drag the app to the Applications folder |
| macOS (Apple Silicon) | `CADDX-PC-Tool-v<x.y.z>-C-macOS-arm64.zip` | Zipped app: extract it and drag the app to the Applications folder |
| Linux x86_64 | `CADDX-PC-Tool-v<x.y.z>-C-Linux-x86_64.deb` | Package install; udev rule set up automatically |
| Linux x86_64 | `CADDX-PC-Tool-v<x.y.z>-C-Linux-x86_64.AppImage` | Portable; udev rule must be set up manually |

---

## Installation

### Windows

**Installer**

1. Double-click the downloaded `…-Windows-x64-Setup.exe` file.
2. If Windows shows "Windows protected your PC", click **More info**, and then **Run anyway**.
3. Follow the setup wizard to finish the installation.

**Portable**

1. Download `…-Windows-x64-Portable.zip` and extract it to a local folder.
2. Double-click `CADDX PC Tool C.exe` to run. No installation is required.

### macOS

1. Download the `.dmg` or `.zip` file. Open the `.dmg` directly, or extract the `.zip` first.
2. Drag `CADDX PC Tool C` into the **Applications** folder.
3. If a security prompt appears the first time you open the app, choose **Open**.

### Linux

**.deb package (recommended)**

The `.deb` package sets up the udev rule automatically. Double-click the `.deb` file to install it with your system's software installer, or run the command below in a terminal.

```bash
sudo apt install ./CADDX-PC-Tool-v<x.y.z>-C-Linux-x86_64.deb
```

**AppImage**

1. Make the file executable: `chmod +x CADDX-PC-Tool-v<x.y.z>-C-Linux-x86_64.AppImage`
2. Double-click the file, or run it from a terminal.
3. The AppImage does not set up the udev rule. Configure it manually as described in Notes.

---

## Usage

### Firmware upgrade

1. Connect the device to your computer with a USB cable, then launch the app. The device is detected and shown on the **Device** page automatically.
2. Click **Connect** on the device card to open the upgrade page.
3. Drag the firmware file into the drop area, or click **select the firmware**.
4. Click **Upgrade**, then confirm in the **Kind tips** dialog.
5. Wait for the progress bar to complete. Keep the USB cable connected and the device powered during the upgrade.

### Gimbal

This section applies to the GM1 V2 and GM3 V2 gimbals. Connect the gimbal, then click **Connect** on the device card to open the gimbal page.

- **Firmware upgrade**: select or drop a gimbal firmware file, then click **Upgrade**.
- **Parameters**: set the gimbal mode, sensitivity, channels, gain, and follow angles. **Load param** reads a parameter file and sends the values to the gimbal; **Save param** saves the current parameters to a file; **Write param** writes the current parameters to the gimbal.
- **Calibration**: **Pos calib** and **Gyro calib**.

---

## Notes

- Keep the USB cable connected and the device powered during an upgrade. Do not unplug the cable, close the app, or power off the device.
- During an upgrade, the device indicator may blink abnormally or the device may restart on its own. This is normal; please wait for the upgrade to finish.
- Use firmware files that match your device model. The tool checks that the firmware and the device match, and will not start an upgrade if they do not.
- Downgrading the device firmware is not recommended.
- Please read the in-app User Agreement (**Settings** → **User Agreement**) before use.
- **Linux**: on distributions that enable ModemManager by default (such as Ubuntu), the tool's udev rule must be configured; otherwise a system service may occupy the device's serial port and cause the upgrade to fail. The `.deb` package configures it automatically. For the AppImage, run the commands below, then unplug and replug the device.

```bash
./CADDX-PC-Tool-v<x.y.z>-C-Linux-x86_64.AppImage --appimage-extract
sudo cp squashfs-root/udev/60-caddx-pc-tool.rules /etc/udev/rules.d/
sudo udevadm control --reload-rules
```

---

## FAQ

**Windows shows "Windows protected your PC"**

The installer is not code-signed, so Windows SmartScreen shows this warning. Click **More info**, and then **Run anyway**.

**The device shows "Unrecognized device" or "Unrecognized device A"**

Make sure your device model is listed in Supported Devices, then unplug and replug the USB cable. If it is still not recognized, try another cable or another USB port.

**"The software is already running"**

Only one instance of Caddx PC Tool can run at a time. Close the open window first.

**The upgrade fails or the device stops responding**

Unplug and replug the device, check the USB cable and power supply, then try again. If the problem persists, contact support with your app version and log files.

**The Linux AppImage fails to start with a missing libfuse.so.2**

Install the FUSE 2 runtime (Ubuntu 22.04: `sudo apt install libfuse2`; Ubuntu 24.04: `sudo apt install libfuse2t64`), or launch the AppImage with the `--appimage-extract-and-run` option.

---

## Support

- Email: support@caddxfpv.com
- Website: https://www.caddxfpv.com
- More contact options are available in the app under **Help** → **Customer Service**.

When reporting an issue, please include the app version (shown at the bottom of the sidebar) and the log files (**Settings** → **Open log folder**).
