# OpenArmX VR Teleoperation APK

English | [中文](README_CN.md)

## Introduction

`openarmx_teleop_vr_apk` stores and distributes the OpenArmX VR device applications.
The application captures OpenXR headset and controller data, sends it to ROS 2 over
the local network, and displays robot camera streams forwarded by ROS.

The repository provides the following packages:

| Device | APK | Notes |
|---|---|---|
| PICO | `openarmx_vr_pico.apk` | Primary maintained version |
| Meta Quest | `openarmx-vr-quest.apk` | Quest device version |

## Features

### VR Data

- Continuously sends the position and orientation of both controllers.
- Sends trigger, grip, A/B/X/Y button, joystick, and joystick-click states.
- Continuously sends the headset position and orientation.
- Controller, headset, and joystick data are independent and can be sent to ROS
  at the same time.
- Supports Gripper Mode (AIM pose) and Hand Mode (GRIP pose).
- Provides Chinese and English interfaces, ROS host IP configuration, and IP
  persistence.
- Provides controller haptic feedback for key mode changes.

The APK captures and sends the complete input state. The companion ROS nodes
determine how those inputs control the arms, grippers or dexterous hands, head,
mobile base, and other robot subsystems.

### VR Video

- Displays the head camera as the primary view.
- Enables or disables both hand camera views with one button.
- Arranges the head view above the left-hand and right-hand views.
- Shows the stream name, resolution, codec, and actual decoding FPS for each view.
- Rotates each view by 180 degrees independently and restores its orientation.
- Keeps the video panel fixed in space or makes it follow the headset view.

Video ports:

| Stream | UDP Port |
|---|---:|
| Head | `5600` |
| Left hand | `5601` |
| Right hand | `5602` |

VR control data is sent to UDP port `5100` on the ROS host by default.

> The current feature set refers to the PICO version. The Meta Quest version may
> not provide the same interface or full feature set.

## Install on PICO

### 1. Enable debugging

1. On PICO, open `Settings > About` and tap the software version repeatedly to
   enable developer mode.
2. Open `Settings > Developer options` and enable USB debugging.
3. Connect PICO to the computer with a USB Type-C data cable and allow USB
   debugging inside the headset.

### 2. Install the application

```bash
sudo apt install adb
adb devices
adb install -r openarmx_vr_pico.apk
```

`adb devices` should report the device state as `device`. The `-r` option keeps
the application data and replaces the installed version. The application is shown
as `openarmx_vr_pico` on PICO.

## Install on Meta Quest

Enable developer mode and USB debugging on Meta Quest, then run:

```bash
adb devices
adb install -r openarmx-vr-quest.apk
```

Chinese users can refer to this guide:
[Enable Meta Quest developer mode](https://www.bilibili.com/video/BV16hyLBpE6L/)

## Basic Workflow

1. Connect the VR device and ROS host to the same local network.
2. Run `hostname -I` on the ROS host to find its IP address.
3. Enter the ROS host IP in the VR application and confirm the connection.
4. Start the ROS VR bridge and teleoperation nodes.
5. For video, start the ROS video forwarder and select **Open Video** in VR.

Companion ROS packages:

- `openarmx_teleop_bridge_vr`: receives VR UDP data and publishes ROS 2 topics.
- `openarmx_teleop_vr`: performs bimanual teleoperation from the VR data.
- `openarmx_head_vision_h264`: encodes and forwards the head and hand camera streams.

See the README files in those ROS packages for launch commands and parameters.

## License

This work is licensed under the Creative Commons Attribution-NonCommercial-
ShareAlike 4.0 International License (CC BY-NC-SA 4.0).

Copyright (c) 2026 Chengdu Changshu Robot Co., Ltd.

See [LICENSE](LICENSE) or visit:
<http://creativecommons.org/licenses/by-nc-sa/4.0/>.

## Author

- **Li QingRan** (李青燃)
- Company: Chengdu Changshu Robot Co., Ltd. (成都长数机器人有限公司)
- Website: <https://openarmx.com/>

## Version

**Current Version: 6.0.0**

## Contact

### Chengdu Changshu Robotics Co., Ltd.

| Contact | Information |
|---|---|
| Email | openarmrobot@gmail.com |
| Phone/WeChat | +86-17746530375 |
| Website | <https://openarmx.com/> |
| Address | Huacheng Machinery Factory, No. 11 Xinye 8th Street, West Area, Tianjin Economic-Technological Development Area |
| Contact person | Mr. Wang |
