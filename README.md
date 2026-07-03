---

# Nexus-N1-Win11-Drivers

Dedicated Windows 11 Driver Pack for Nexus AI Station N1 Devices

---

## ⚠️ READ FIRST

Since the Nexus N1 lacks native network drivers after a clean Windows 11 installation, resulting in no internet access, **please make sure to download this driver pack onto a USB drive** using another internet-connected computer **BEFORE** installing the OS!

> 💡 Recommendation: Extract the entire driver pack to the root directory of your USB drive, and install the drivers directly from the USB drive after the OS installation is complete. This avoids the deadlock situation where you cannot download drivers due to no network access.

---

## 📋 Project Description

This repository serves as a curated collection of essential hardware drivers required for running Windows 11 on the Nexus AI Station N1. It includes proprietary onboard drivers that are not indexed by standard driver tools (such as Driver Genius, Driver Life, 360 Driver Master), resolving issues where hardware components cannot be recognized after OS installation.

**Target Device**: Nexus AI Station N1
**Supported OS**: Windows 11 64-bit (21H2/22H2/23H2/24H2)
**Driver Source**: Extracted from the official driver package
**Total Components**: 55 driver components

---

## 📦 Driver List

### 🔌 Chipset - Must Be Installed First

* AMD ACP Audio Bus Driver
* AMD I2C/SMBus Driver
* AMD PCIe Bridge Extension Driver
* AMD PSP Secure Processor Driver
* AMD Platform Management Framework (PMF) Driver
* AMD GPIO Controller Driver
* AMD µPEP Power Management Driver
* AMD SD/eMMC Host Controller Driver

### 🌐 LAN/WLAN - Restores Network Access After Installation

* **Aquantia AQC107 10GbE Driver** (aqnic650) - Onboard 2.5G/10G Ethernet Port
* AMD USB4 Network Driver
* AMD SD Wireless Extension Driver

> ✅ **Installation Tip**: Once this component is installed, your internet connection will be restored. You can then use Windows Update to automatically download and update the remaining drivers.

### 🎮 Graphics

* AMD Radeon Graphics Driver (amdxe)
* AMD Vulkan Driver (amdvlk)
* AMD OpenGL Driver (amdogl)
* AMD OpenCL Compute Driver (amdocl)
* NVIDIA Display Output Driver (nv_dispig)
* NVIDIA Platform Control Framework Driver

### 🔊 Audio

* AMD ACP All-in-One Audio Driver
* AMD Audio DSP Driver
* AMD Bluetooth Audio Driver (SCO/ACX)
* NVIDIA HD Audio Driver
* Voice Clarity Audio Component Driver

### 🔌 USB & Type-C

* AMD USB4/Thunderbolt Connection Manager Driver
* AMD USB4 PCIe Filter Driver
* AMD USB Hub Filter Driver
* AMD USB Function Driver
* AMD Wireless Button Driver

### 📝 Other System Drivers

* JMicron JMB585 SATA Controller Driver
* Realtek USB Card Reader Driver
* AMD Sensor Fusion Hub (SFH) HID Driver
* ATI Hardware Watchdog Driver
* System Button Driver
* Printer Compatibility Driver

---

## 🚀 Recommended Installation Order

To prevent conflicts or errors, please strictly follow the installation order below:

| Order | Driver Category | Priority | Note |
| --- | --- | --- | --- |
| 1 | Core Chipset Drivers | ⭐⭐⭐⭐⭐ | Reboot your PC before moving to the next step |
| 2 | Network Drivers (LAN/WLAN) | ⭐⭐⭐⭐⭐ | Restores internet connection immediately after install |
| 3 | USB/Type-C Drivers | ⭐⭐⭐⭐ | Fixes external device recognition issues |
| 4 | Core Graphics Drivers | ⭐⭐⭐⭐ | Restores native resolution and hardware acceleration |
| 5 | Audio Drivers | ⭐⭐⭐ | Restores sound output |
| 6 | Miscellaneous Drivers | ⭐⭐⭐ | Can be automatically filled in via Windows Update |

---

## 💻 Installation Methods

### Method 1: Manual Installation

1. Extract this driver package to a USB drive or local hard drive.
2. Right-click the **Start Menu** and select **Device Manager**.
3. Locate the unknown devices marked with a yellow exclamation mark.
4. Right-click the device and choose **Update driver** -> **Browse my computer for drivers**.
5. Select the corresponding driver folder, and click Next to finish the installation.
6. Install them one by one according to the recommended order above. Select reboot when prompted.

### Method 2: Batch Auto-Installation [Recommended!]

1. Run **PowerShell** as an Administrator.
2. Execute the following command to batch install all drivers:
```PowerShell
Get-ChildItem -Path "C:\Harbor_AI_Drivers" -Recurse -Filter *.inf | ForEach-Object {pnputil /add-driver $_.FullName /install}
```



*Note: You can adjust the path command based on your extraction location. In this example, the package is extracted directly to the root of the C drive.*

Wait for all drivers to finish installing, then reboot your computer!

---

## 🤝 Contributions

If you find any missing drivers or more compatible versions, feel free to submit an Issue or Pull Request (PR)!
If this driver pack helped you, please give this repository a ⭐ Star to support it!

---

## ⚖️ Disclaimer

* This driver package is provided for educational and community sharing purposes only. All driver copyrights belong to their respective original manufacturers.
* Please backup your important data before installing any drivers. This repository is not responsible for any system issues or data loss caused by driver installation.
* It is highly recommended to obtain the latest drivers from official channels. This repository only serves as a collection, organization, and backup archive.
* If any manufacturer considers this repository to be an infringement, please contact me to have it removed.



# Nexus-N1-Win11-Drivers

Nexus AI Station N1 设备安装 Windows 11 专用驱动包

---

## ⚠️ 提示

由于 Nexus N1 原生安装 Windows 11 后会缺失网卡驱动导致无法联网，**请务必在装机前**，使用其他可联网的电脑将本驱动包下载到 U 盘中备用！

> 💡 建议：将整个驱动包解压到 U 盘根目录，安装完系统后直接从 U 盘安装驱动，避免无网络无法下载驱动的死锁问题。

---

## 📋 项目说明

本仓库专门收集并打包了 Nexus AI Station N1 运行 Windows 11 系统所需的关键硬件驱动。包含市面上通用驱动软件（如驱动精灵、驱动人生、360驱动大师）未收录的板载特制驱动，解决安装系统后硬件无法识别的问题。

**适用设备**：Nexus AI Station N1
**适用系统**：Windows 11 64位 (21H2/22H2/23H2/24H2)
**驱动版本**：基于官方驱动包提取
**驱动总数**：55个驱动组件

---

## 📦 包含驱动列表

### 🔌 核心芯片组驱动 (Chipset) - 必须优先安装
- AMD ACP 音频总线驱动
- AMD I2C/SMBus 总线驱动
- AMD PCIe 桥接扩展驱动
- AMD PSP 安全处理器驱动
- AMD 平台管理框架 (PMF) 驱动
- AMD GPIO 控制器驱动
- AMD 微型PEP电源管理驱动
- AMD SD/eMMC 主控制器驱动

### 🌐 有线/无线网卡驱动 (LAN/WLAN) - 安装后恢复网络
- **Aquantia AQC107 万兆网卡驱动** (aqnic650) - 板载2.5G/10G网口
- AMD USB4 网络驱动
- AMD SD 无线扩展驱动

> ✅ **安装提示**：装完此项后即可联网，后续可通过Windows Update自动更新剩余驱动

### 🎮 核心显卡/显示驱动 (Graphics)
- AMD Radeon 核显驱动 (amdxe)
- AMD Vulkan 驱动 (amdvlk)
- AMD OpenGL 驱动 (amdogl)
- AMD OpenCL 计算驱动 (amdocl)
- NVIDIA 显示输出驱动 (nv_dispig)
- NVIDIA 平台控制框架驱动

### 🔊 板载音频驱动 (Audio)
- AMD ACP 全系列音频驱动
- AMD 音频DSP驱动
- AMD 蓝牙音频驱动 (SCO/ACX)
- NVIDIA HD 音频驱动
- 语音清晰度音频组件驱动

### 🔌 USB与Type-C驱动
- AMD USB4/雷电 连接管理器驱动
- AMD USB4 PCIe 过滤驱动
- AMD USB 集线器过滤驱动
- AMD USB 功能驱动
- AMD 无线按钮驱动

### 📝 其他系统驱动
- JMicron JMB585 SATA控制器驱动
- Realtek USB 读卡器驱动
- AMD 传感器融合中心 (SFH) HID驱动
- ATI 硬件看门狗驱动
- 系统按钮驱动
- 打印机兼容驱动

---

## 🚀 推荐安装顺序

为避免出现问题，请严格按照以下顺序安装驱动：

| 顺序 | 驱动类别 | 重要性 | 说明 |
|------|----------|--------|------|
| 1 | 核心芯片组驱动 | ⭐⭐⭐⭐⭐ | 重启后再进行下一步 |
| 2 | 有线网卡驱动 | ⭐⭐⭐⭐⭐ | 安装后即可联网 |
| 3 | USB/Type-C驱动 | ⭐⭐⭐⭐ | 解决外接设备识别问题 |
| 4 | 核心显卡驱动 | ⭐⭐⭐⭐ | 恢复正常分辨率和硬件加速 |
| 5 | 音频驱动 | ⭐⭐⭐ | 恢复声音输出 |
| 6 | 其他剩余驱动 | ⭐⭐⭐ | 可通过Windows Update自动补全 |

---

## 💻 安装方法

### 方法一：手动安装
1. 将本驱动包解压到 U 盘或本地硬盘
2. 右键点击「开始菜单」→「设备管理器」
3. 找到带黄色感叹号的未知设备
4. 右键选择「更新驱动程序」→「浏览我的计算机以查找驱动程序」
5. 选择对应驱动文件夹，点击下一步完成安装
6. 按照上述安装顺序逐个安装，提示重启时选择重启

### 方法二：批量自动安装（推荐！）
1. 以管理员身份运行命令提示符 (PowerShell) 
2. 执行以下命令批量安装：
   ```powershell
   Get-ChildItem -Path "C:\Harbor_AI_Drivers" -Recurse -Filter *.inf | ForEach-Object {pnputil /add-driver $_.FullName /install}
注意：命令可以根据解压的位置自行调整，我这里是直接解压到的C盘。
等待所有驱动安装完成后重启电脑即可！

<img width="780" height="650" alt="image" src="https://github.com/user-attachments/assets/ee2e7e4c-ad32-4382-958f-7ebda2139fe9" />

🤝 贡献说明
如果您发现有缺失的驱动或者更兼容的版本，欢迎提交 Issue 或 PR！
如果这个驱动包帮到了你，欢迎点个 ⭐ Star 支持一下！

⚖️ 免责声明
本驱动包仅用于学习交流目的，所有驱动版权归原厂商所有
安装驱动前请自行备份重要数据，因安装驱动造成的任何问题本仓库概不负责
建议从官方渠道获取最新驱动，本仓库仅做收集整理和备份
如果厂商认为本仓库侵权，请联系删除
