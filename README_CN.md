## 📦 包简介

`openarmx_teleop_vr_apk` 是 OpenArmX 的 VR 遥操作 APK 安装包仓库，专门用于集中存放和分发 VR 设备端桥接应用安装包，方便用户下载并完成设备部署。

## Pico

## 1) 连接设备

1. 开启开发者模式并进入 USB 调试模式。  
   开启开发者模式：`设置 > 关于本机 > 连续点击软件版本号`  
   开启 USB 调试：`设置 > 开发者选项 > USB 调试`
2. 使用 USB Type-C 数据线将 Pico 连接到 PC。

## 2) 安装 Pico 桥接 APK

```bash
# 安装 ADB 工具
sudo apt install adb

# 进入 APK 所在目录
cd <你的下载目录>

# 安装桥接软件
adb install openarmx-vr-pico.apk
```

## Meta quest

安装方法和pico类似，先打开**开发者模式**，再连接设备到 PC 。再通过 adb 安装软件

但 Meta quest 的安装步骤非常繁琐，中国用户可以看这个视频 [打开开发者模式](https://www.bilibili.com/video/BV16hyLBpE6L?buvid=XU5420159AA4697154A0DC4C9BD238EE7A6BC&from_spmid=united.player-video-detail.relatedvideo.0&is_story_h5=false&mid=xX5%2BKHmnsR16JMhsd10cQH8FTQ%2FSZMtL1rElX6M3iMo%3D&plat_id=116&share_from=ugc&share_medium=android&share_plat=android&share_session_id=82fb3460-d9a1-4610-8286-987995bca399&share_source=WEIXIN&share_tag=s_i&spmid=united.player-video-detail.0.0&timestamp=1774775521&unique_k=MR4mqSC&up_id=32985573&vd_source=b22b744a9e6ff37e0464bd12a5e08df2)


## 许可证

本作品采用知识共享 署名-非商业性使用-相同方式共享 4.0 国际许可协议 (CC BY-NC-SA 4.0) 进行许可。

版权所有 (c) 2026 成都长数机器人有限公司 (Chengdu Changshu Robot Co., Ltd.)

详情请参阅 [LICENSE_CN.md](LICENSE) 文件或访问：http://creativecommons.org/licenses/by-nc-sa/4.0/

## 作者

- **Li QingRan** (李青燃)
- 公司: Chengdu Changshu Robot Co., Ltd. (成都长数机器人有限公司)
- 网站: https://openarmx.com/

## 版本

**当前版本**：6.0.0

## 致谢

本包是 OpenArmX 机器人平台生态系统的一部分，专为协作机器人领域的研究和工业应用而开发。

---

## 📞 联系我们

### 成都长数机器人有限公司
**Chengdu Changshu Robotics Co., Ltd.**

| 联系方式 | 信息 |
|---------|------|
| 📧 邮箱 | openarmrobot@gmail.com |
| 📱 电话/微信 | +86-17746530375 |
| 🌐 官网 | <https://openarmx.com/> |
| 📍 地址 | 天津经济技术开发区西区新业八街11号华诚机械厂 |
| 👤 联系人 | 王先生 |
