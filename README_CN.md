# OpenArmX VR 遥操作 APK

[English](README.md) | 中文

## 包简介

`openarmx_teleop_vr_apk` 用于存放和发布 OpenArmX VR 设备端应用。应用采集
OpenXR 头显和左右手柄数据，通过局域网发送给 ROS 2，并可接收 ROS 端转发的
机器人相机画面。

仓库提供以下安装包：

| 设备 | APK | 说明 |
|---|---|---|
| PICO | `openarmx_vr_pico.apk` | 当前主要维护版本 |
| Meta Quest | `openarmx-vr-quest.apk` | Quest 设备版本 |

## 已有功能

### VR 数据发送

- 持续发送左右手柄的位置和姿态。
- 发送扳机、握把、A/B/X/Y 按键、左右摇杆和摇杆按键状态。
- 持续发送头显位置和姿态。
- 左右手柄、头部和摇杆数据相互独立，可同时发送给 ROS 端。
- 支持夹爪模式（AIM 位姿）和手部模式（GRIP 位姿）。
- 支持中英文界面、ROS 主机 IP 设置和 IP 保存。
- 关键模式切换提供手柄震动反馈。

APK 负责采集和发送完整输入数据。双臂、夹爪或灵巧手、头部、底盘等具体控制
行为由配套 ROS 节点决定。

### VR 视频

- 默认显示头部相机主画面。
- 可通过同一个按钮开启或关闭左右手相机画面。
- 三路视频采用“头部在上、左右手在下”的布局。
- 每路画面独立显示名称、分辨率、编码格式和实际解码 FPS。
- 每路画面均可独立旋转 180 度或恢复方向。
- 视频面板可固定在空间中，也可开启“跟随视野”。

视频端口分配如下：

| 视频 | UDP 端口 |
|---|---:|
| 头部 | `5600` |
| 左手 | `5601` |
| 右手 | `5602` |

VR 控制数据默认发送到 ROS 主机的 UDP `5100` 端口。

> 当前新增功能以 PICO 版本为准，Meta Quest 版本不保证具备完全相同的界面和功能。

## 安装 PICO APK

### 1. 开启调试模式

1. 在 PICO 中进入 `设置 > 关于本机`，连续点击软件版本号开启开发者模式。
2. 进入 `设置 > 开发者选项`，开启 USB 调试。
3. 使用 USB Type-C 数据线连接 PICO 和电脑，并在头显中允许 USB 调试。

### 2. 安装应用

```bash
sudo apt install adb
adb devices
adb install -r openarmx_vr_pico.apk
```

`adb devices` 应将设备状态显示为 `device`。`-r` 表示保留应用数据并覆盖安装。
安装后，PICO 中显示的应用名称为 `openarmx_vr_pico`。

## 安装 Meta Quest APK

Meta Quest 同样需要先开启开发者模式和 USB 调试，然后执行：

```bash
adb devices
adb install -r openarmx-vr-quest.apk
```

中国用户可参考：[开启 Meta Quest 开发者模式](https://www.bilibili.com/video/BV16hyLBpE6L/)

## 基本使用流程

1. 确保 VR 设备和 ROS 主机位于同一局域网。
2. 在 ROS 主机执行 `hostname -I` 获取主机 IP。
3. 在 VR 应用中填写 ROS 主机 IP 并确认连接。
4. 启动 ROS 端 VR 桥接与遥操作节点。
5. 需要视频时，启动 ROS 端视频转发节点，再在 VR 中点击“打开视频”。

配套 ROS 包：

- `openarmx_teleop_bridge_vr`：接收 VR UDP 数据并发布 ROS 2 话题。
- `openarmx_teleop_vr`：根据 VR 数据执行双臂遥操作控制。
- `openarmx_head_vision_h264`：编码并转发头部及左右手相机画面。

详细启动参数和命令请查看上述 ROS 包内的 README。

## 许可证

本作品采用知识共享署名-非商业性使用-相同方式共享 4.0 国际许可协议
（CC BY-NC-SA 4.0）进行许可。

版权所有 (c) 2026 成都长数机器人有限公司

详情请参阅 [LICENSE](LICENSE) 或访问：<http://creativecommons.org/licenses/by-nc-sa/4.0/>

## 作者

- **Li QingRan**（李青燃）
- 公司：成都长数机器人有限公司
- 网站：<https://openarmx.com/>

## 版本

**当前版本：6.0.0**

## 联系我们

### 成都长数机器人有限公司

| 联系方式 | 信息 |
|---|---|
| 邮箱 | openarmrobot@gmail.com |
| 电话/微信 | +86-17746530375 |
| 官网 | <https://openarmx.com/> |
| 地址 | 天津经济技术开发区西区新业八街 11 号华诚机械厂 |
| 联系人 | 王先生 |
