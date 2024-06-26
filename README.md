# Scrcpy-mask

[中文介绍](./README-zh.md)

To achieve computer control of Android devices, I developed a cross-platform desktop client using Tarui + Vue 3 + Rust. This client provides visual mouse and keyboard mapping configuration, enabling multi-touch operations similar to Android emulators through key mapping, with millisecond-level response time. This tool can be widely used for controlling Android devices from computers to play mobile games, providing a smooth touch experience.

This project only implements the Scrcpy control protocol and **does not provide Screen mirroring**. Because screen mirroring may involve latency and blurriness issues, this project takes a different approach by directly abandoning screen mirroring and instead using a transparent mask to display the content behind the window (which can be AVD, low-latency screen mirroring provided by your phone manufacturers, etc.), Completely eliminates the problem of poor screen casting experience inherent in Scrcpy.

## Features

- [x] Wired and wireless connections to Android devices
- [x] Start scrcpy-server and connect to it
- [x] Implement scrcpy client control protocol
- [x] Mouse and keyboard key mapping
- [x] Visually setting the mapping
- [x] Key mapping config import and export
- [x] Update check
- [x] Switch between key mapping and input-text box
- [x] Internationalization (i18n)
- [ ] Gamepad key mapping
- [ ] Better macro support
- [x] Provide external control through websocket, see [external control](https://github.com/AkiChase/scrcpy-mask-external-control)
- [ ] Help document

## Demonstration video

- [如何用电脑玩FPS手游？这样的“安卓模拟器”，也不是不可以-哔哩哔哩](https://www.bilibili.com/video/BV1EU411Z7TC/?share_source=copy_web&vd_source=36923115230d8a46ae8b587fc5348e6e)
- [M 系列 Mac 电脑玩王者，暃排位实录，使用 Android Stuido 模拟器和开源 Scrcpy Mask 按键映射工具-哔哩哔哩](https://b23.tv/q6iDW1w)
- [自制跨平台开源项目 Scrcpy Mask ，像模拟器一样用键鼠控制任意安卓设备！以 M 系列芯片 MacBook 打王者为例-哔哩哔哩](https://b23.tv/gqmriXr)
- [如何用 PC 控制安卓手机打王者？只要思想不滑坡，办法总比困难多！-哔哩哔哩](https://b23.tv/dmUOpff)
- [M 芯片 Mac 怎么用 Android Studio 模拟器打王者？这是 Up 耗时数个月给出的答案-哔哩哔哩](https://b23.tv/ckJgyK5)

## Implementation principle

- [Scrcpy Mask 实现原理剖析，如何像模拟器一样用键鼠控制你的安卓设备？架构、通信篇 - 掘金](https://juejin.cn/post/7366799820734939199)
- [Scrcpy Mask 实现原理剖析，如何像模拟器一样用键鼠控制你的安卓设备？前端可视化、按键映射篇 - 掘金](https://juejin.cn/post/7367620233140748299)
- [Scrcpy Mask 实现原理剖析，如何在前端实现王者荣耀中技能的准确释放？ - 掘金](https://juejin.cn/post/7367568884198047807)

## Screenshot

- Device control

![](https://pic.superbed.cc/item/6637190cf989f2fb975b6162.png)

- Key mapping setting

![](https://pic.superbed.cc/item/66371911f989f2fb975b62a3.png)

- Mask above game
 
![](https://pic.superbed.cc/item/66373c8cf989f2fb97679dfd.png)

![](https://pic.superbed.cc/item/6649cf0cfcada11d37c05b5e.jpg)

## Basic using

1. Install software suitable for your system platform from [releases](https://github.com/AkiChase/scrcpy-mask/releases)
2. Identify your Android device type
   1. For physical devices like phones or tablets
      1. You need to solve the problem of screen casting on your own. Recommend using the official screen mirror method of your device brand to achieve the minimum delay
      2. Enable ADB debugging on your device via USB or wirelessly, then connect it to your computer.
   2. For emulator, you don't need screen mirror, and emulator generally default to enabling ADB wired debugging. So this is the best way for game, I think.
3. Launch the software and navigate to the Device page.
   1. Find your device among the available devices (if not found, please search for how to enable ADB debugging for your device).
   2. Right-click on your device and choose "Get Screen Size". Use the obtained screen size as a reference and enter the device's width and height correctly. Note: If the width or height is incorrect (for example, they are reversed in portrait and landscape modes), all touch operations will be ignored, but no error message will appear.
   3. Right-click on your device again and choose "Control this device".
4. Navigate to the Settings page -> Mask Settings, and set the width and height of the mask to a certain multiple of the device's size to ensure the mask size is appropriate.
5. Navigate to the Mask page where you can see a transparent mask. Next, adjust and move your emulator window or screen mirroring window to align the displayed content area with the transparent mask area.
6. Navigate to the Key mapping page and switch or edit the key mapping configs.
7. Return to the Mask page and start enjoying.

## Contribution.

If you are interested in this project, you are welcome to submit pull request or issue. But my time and energy is limited, so I may not be able to deal with it all.

[![Star History Chart](https://api.star-history.com/svg?repos=AkiChase/scrcpy-mask&type=Date)](https://star-history.com/#AkiChase/scrcpy-mask&Date)
