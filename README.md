# Huawei Mate 9 KernelSU (EMUI 9.1)

![KernelSU](https://img.shields.io/badge/KernelSU-v0.9.2-green) ![Device](https://img.shields.io/badge/Device-Huawei%20Mate%209-blue) ![EMUI](https://img.shields.io/badge/EMUI-9.1-red)

> **声明 / Disclaimer**：
> 刷机有风险，操作需谨慎。本项目仅供技术交流，对于刷入后可能导致的设备损坏（如变砖、数据丢失等），作者不承担任何责任。
> **请务必确保你的设备已解锁 Bootloader。**

## 📖 项目简介 | Introduction

这是一个适用于 **Huawei Mate 9 (MHA-AL00/L29)** 运行 **EMUI 9.1** 系统的定制内核，集成了 **KernelSU v0.9.2**。

**本项目的初衷：**
之前网络上曾有大神发布过适配 EMUI 9.1 的内核，但遗憾的是原仓库已被删除。为了防止 Mate 9 这款“一代神机”的玩机资源断代，也为了让 EMUI 9.1 用户能继续体验 KernelSU，我基于开源代码重新编译并制作了本项目。

## 💡 为什么要使用 KernelSU？ (vs Magisk)

对于华为 EMUI 8.0/9.0/9.1 机型，使用传统的 Magisk Root 方案存在极大的痛点，本内核通过 KernelSU 完美解决了这些问题：

### 🚫 传统 Magisk 方案的痛点：
在 EMUI 9.x 上，Magisk 必须通过修补 `Recovery_Ramdisk` 来实现 Root。这带来了两个严重问题：
1.  **开机繁琐**：每次开机必须按住特定的组合键（如音量上+电源）进入 Recovery 模式才能加载 Root 环境，否则就是无 Root 状态。
2.  **维护困难**：一旦不小心直接引导进入了原系统（未按组合键），系统会自动恢复官方 Recovery，导致 Root 丢失，必须连接电脑重新刷入修补后的镜像。
3.  **功能阉割**：占用了 Recovery 分区，导致原本的恢复模式不可用。

### ✅ 本 KernelSU 内核的优势：
* **原生启动**：直接集成在 kernel 内核中，**按电源键正常开机即可拥有 Root 权限**，无需任何组合键。
* **独立共存**：不修改 Recovery 分区，你的官方 Recovery 或 TWRP 可以完美保留，救砖、双清更方便。
* **更隐蔽**：基于内核空间的 Root 方案，拥有更强的控制能力。

## 📱 适用机型 | Supported Devices

* **机型**：Huawei Mate 9 (MHA-AL00 / MHA-TL00 / MHA-L29)
* **系统版本**：EMUI 9.1 (基于 Android 9)（也许鸿蒙也可以，未经测试，谨慎刷入）
    * ⚠️ **警告**：请勿在 EMUI 8.0、EMUI 9.0 上尝试，将会导致无限重启。

## 🛠️ 安装方法 | Installation

### 前置条件
1.  手机必须已经**解锁 Bootloader**（目前 Mate 9 通常需要通过拆机短接测试点的方式解锁）。短接测试点解锁工具：[PotatoNV](https://github.com/mashed-potatoes/PotatoNV)
2.  电脑已配置好 `adb` 和 `fastboot` 环境。

### 刷入步骤
1.  下载本仓库 Release 中的镜像文件。
2.  手机进入 Fastboot 模式（连接电脑，按住音量下+电源键）。
3.  执行以下命令刷入内核：
    ```bash
    fastboot flash kernel <你的内核文件名>.img
    ```
4.  重启手机：
    ```bash
    fastboot reboot
    ```
5.  开机后安装 [KernelSU Manager](https://github.com/tiann/KernelSU/releases) APP 即可管理权限。必须安装0.9.2版本！其他版本可能不兼容。


## 🤝 致谢 | Credits

* 感谢 **KernelSU** 团队提供的出色工作。
* 感谢之前为 Mate 9 适配过内核的前辈们（yunmo2007 等），是你们的工作给了我灵感。

---
*如果你觉得这个项目对你有帮助，请点亮右上角的 ⭐️ Star，让更多 Mate 9 钉子户看到！*
