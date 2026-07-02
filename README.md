# Nexus-N1-Win11-Drivers

Nexus AI Station N1 设备安装 Windows 11 专用驱动包

---

## ⚠️ 提示（READ FIRST）

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
1. 以管理员身份运行命令提示符 (CMD) 
2. 执行以下命令批量安装：
   ```cmd
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
