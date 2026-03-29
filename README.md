## 📦 Package Introduction

`openarmx_teleop_vr_apk` is the VR teleoperation APK repository for OpenArmX, specifically designed for centralized storage and distribution of VR device-side bridge application packages, facilitating user downloads and device deployment.

## Pico

## 1) Connect Device

1. Enable developer mode and enter USB debugging mode.
   Enable developer mode: `Settings > About > Tap software version number multiple times`
   Enable USB debugging: `Settings > Developer options > USB debugging`
2. Connect Pico to PC using a USB Type-C data cable.

## 2) Install Pico Bridge APK

```bash
# Install ADB tools
sudo apt install adb

# Navigate to the APK directory
cd <your_download_directory>

# Install the bridge application
adb install openarmx-vr-pico.apk
```

## Meta Quest

The installation method is similar to Pico. First enable **developer mode**, then connect the device to PC, and install the application via adb.

However, the Meta Quest installation process is quite complicated. Chinese users can watch this video: [Enable Developer Mode](https://www.bilibili.com/video/BV16hyLBpE6L?buvid=XU5420159AA4697154A0DC4C9BD238EE7A6BC&from_spmid=united.player-video-detail.relatedvideo.0&is_story_h5=false&mid=xX5%2BKHmnsR16JMhsd10cQH8FTQ%2FSZMtL1rElX6M3iMo%3D&plat_id=116&share_from=ugc&share_medium=android&share_plat=android&share_session_id=82fb3460-d9a1-4610-8286-987995bca399&share_source=WEIXIN&share_tag=s_i&spmid=united.player-video-detail.0.0&timestamp=1774775521&unique_k=MR4mqSC&up_id=32985573&vd_source=b22b744a9e6ff37e0464bd12a5e08df2)


## License

This work is licensed under a Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License (CC BY-NC-SA 4.0).

Copyright (c) 2026 Chengdu Changshu Robot Co., Ltd.

For details, please refer to the [LICENSE.md](LICENSE) file or visit: http://creativecommons.org/licenses/by-nc-sa/4.0/

## Author

- **Li QingRan** (李青燃)
- Company: Chengdu Changshu Robot Co., Ltd. (成都长数机器人有限公司)
- Website: https://openarmx.com/

## Version

**Current Version**: 6.0.0

## Acknowledgments

This package is part of the OpenArmX robot platform ecosystem, developed specifically for research and industrial applications in the collaborative robotics field.

---

## 📞 Contact Us

### Chengdu Changshu Robotics Co., Ltd.
**成都长数机器人有限公司**

| Contact | Information |
|---------|------------|
| 📧 Email | openarmrobot@gmail.com |
| 📱 Phone/WeChat | +86-17746530375 |
| 🌐 Website | <https://openarmx.com/> |
| 📍 Address | Huacheng Machinery Factory, No. 11 Xinye 8th Street, West Area, Tianjin Economic-Technological Development Area |
| 👤 Contact Person | Mr. Wang |
