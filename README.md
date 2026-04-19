# Intel VCA2 Documentation | Intel Visual Compute Accelerator 2 Deployment Guide

![Intel VCA2 card / Intel VCA2 外观图](./vca2显卡展示图片.png)

**中文简介**

这是一个围绕 **Intel VCA2 / Intel Visual Compute Accelerator 2** 的整理型文档仓库，重点覆盖：

- 硬件结构与定位
- 平台兼容性与前置条件
- Host 部署思路
- Node 镜像与启动模式
- 网络、SSH 与服务部署
- 风险、限制与 FAQ

这个仓库对外只呈现整理后的使用文档，适合已经拿到完整官方驱动资料、想先把整体思路理清再动手的人。

**English Summary**

This repository provides **structured Intel VCA2 documentation** for users who want a clearer path before working with the full official driver and image package.

It focuses on:

- Intel VCA2 hardware overview
- compatibility and platform requirements
- host deployment workflow
- node images, RAMDisk vs BlockIO
- networking, SSH, and service deployment
- limitations, risks, and troubleshooting

## SEO Keywords

`Intel VCA2`, `Intel Visual Compute Accelerator 2`, `Intel VCA2 documentation`, `Intel VCA2 guide`, `Intel VCA2 deployment`, `Intel VCA2 driver`, `Intel VCA2 image`, `Intel VCA2 BlockIO`, `Intel VCA2 RAMDisk`, `Intel VCA2 Jellyfin`, `Intel VCA2 transcoding`, `Intel VCA2 compatibility`

## Start Here

### 中文入口

- [文档总览](./docs/00-文档导航.md)
- [快速开始](./docs/08-快速开始.md)
- [VCA2 概览与硬件结构](./docs/01-VCA2概览与硬件结构.md)
- [兼容性、前置条件与准备清单](./docs/02-兼容性与准备清单.md)
- [宿主机部署指南](./docs/03-宿主机部署指南.md)
- [Node 镜像、启动模式与持久化](./docs/04-Node镜像与启动模式.md)
- [网络、SSH 与服务部署](./docs/05-网络访问与服务部署.md)
- [应用场景、风险、排错与 FAQ](./docs/06-应用限制风险与FAQ.md)
- [文档说明与使用边界](./docs/07-文档说明与使用边界.md)

### English Entry

- [English Documentation Guide](./docs/README.en.md)
- [English Quick Start](./docs/QUICKSTART.en.md)
- [English Overview and Hardware Structure](./docs/01-overview.en.md)
- [English Compatibility and Preparation Checklist](./docs/02-compatibility-and-checklist.en.md)
- [English Host Deployment Guide](./docs/03-host-deployment.en.md)
- [English Node Images and Boot Modes](./docs/04-node-images-and-boot-modes.en.md)
- [English Networking, SSH, and Service Deployment](./docs/05-networking-ssh-and-services.en.md)
- [English Risks, Limitations, and FAQ](./docs/06-risks-limitations-and-faq.en.md)
- [English Documentation Scope and Boundaries](./docs/07-scope-and-boundaries.en.md)

## What This Repository Covers

### 中文

这套文档主要帮助读者回答这些问题：

- VCA2 到底是什么，为什么它不是普通显卡
- 为什么普通家用平台大概率点不亮
- 为什么虚拟机直通通常不可行
- 为什么 BlockIO 更适合长期保留节点环境
- 节点怎么联网、怎么 SSH、怎么部署媒体服务
- 它到底适合做什么，不适合做什么

### English

This documentation is designed to answer:

- What Intel VCA2 actually is
- Why it behaves more like a multi-node server card than a normal GPU
- Why consumer platforms often fail to initialize it properly
- Why VFIO / VM passthrough is usually not the right path
- Why BlockIO is generally the better long-term boot mode
- How nodes are accessed, networked, and used for services such as media workloads

## Scope and Boundaries

### 中文

本仓库已经尽量把信息整理成可读文档，但以下内容仍应优先以配套的**完整官方驱动、镜像和相关资料**为准：

- 驱动安装命令
- 节点管理命令
- 镜像挂载命令
- 默认账号与初始密码
- 工具目录、脚本路径、服务名
- 版本对应关系

原因不是来源不可靠，而是：

- Intel 官网公开下载链路大多已经失效
- 但配套资料库中保存了完整官方驱动、镜像和相关资料
- 不同官方资料包内部的脚本、目录结构、工具版本仍可能存在差异

### English

This repository is a **structured guide**, not a replacement for the full official package.

For the following items, always defer to the official driver and image package:

- exact installation commands
- node management commands
- image mounting commands
- default credentials
- script paths, tool directories, and service names
- version-specific mappings

## Official Materials Package

### 中文

补充资料来源：

- <https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw>

目前公开页可确认的信息：

- `17.09 GB`
- `479 files`
- `91 subfolders`

结合现有资料背景，这个资料库保存了完整官方驱动、镜像和相关资料；本仓库则负责把使用思路整理清楚。

### English

The linked Mega folder is understood as the **complete official driver, image, and related materials package**, while this repository serves as the structured public-facing documentation layer.

The highlighted package index is embedded directly below in this README.

## 官方驱动与依赖文件索引

这部分直接展示 **Intel VCA2 官方资料包** 里最值得优先关注的驱动、镜像、依赖和工具文件，方便在 GitHub 首页直接查找。

以下快捷链接基于公开资料目录在 `2026-04-19` 的可见内容生成。文件作用说明主要依据官方文件名、目录结构和包名归纳；真正执行安装、挂载、刷写或镜像制作时，仍应以包内说明文档和脚本为准。

### 宿主机驱动与开发相关包

- `intelvisualcomputeaccelerator_host_ubuntu_16.04.3_k4.14.20_2.3.26.zip`
  说明：Ubuntu 宿主机驱动与管理工具包，适合 Ubuntu 16.04.3 路线。
  快捷下载：[打开文件](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/folder/CI0DUaoY/file/eZlRhaSR)
- `intelvisualcomputeaccelerator_host_centos_7.4_k4.14.20_2.3.26.zip`
  说明：CentOS 宿主机驱动与管理工具包，适合 CentOS 7.4 路线。
  快捷下载：[打开文件](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/folder/CI0DUaoY/file/eA9hHQ4b)
- `intelvisualcomputeaccelerator_host_debian_8.7_k4.14.20_2.3.26.zip`
  说明：Debian 宿主机驱动与管理工具包，适合 Debian 8.7 路线。
  快捷下载：[打开文件](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/folder/CI0DUaoY/file/GJljSCbK)
- `intelvisualcomputeaccelerator_kernels_development_package_2.3.26.zip`
  说明：内核开发相关包，适合需要编译或适配内核模块的场景。
  快捷下载：[打开文件](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/folder/CI0DUaoY/file/XF8hiIqL)
- `intelvisualcomputeaccelerator_build_scripts_2.3.26.zip`
  说明：构建脚本集合，适合配合开发包和源码包一起查看。
  快捷下载：[打开文件](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/folder/CI0DUaoY/file/fI9hlYjY)
- `intelvisualcomputeaccelerator_sources_2.3.26.zip`
  说明：源码包，适合做二次研究、脚本考证和版本比对。
  快捷下载：[打开文件](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/folder/CI0DUaoY/file/2Qs1yAjC)
- `intelvisualcomputeaccelerator_bios_2.3.26.zip`
  说明：VCA2 固件相关 BIOS 包。
  快捷下载：[打开文件](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/folder/CI0DUaoY/file/KEtTRajQ)
- `intelvisualcomputeaccelerator_eeprom_2.3.26.zip`
  说明：EEPROM 相关小包，通常与底层固件维护有关。
  快捷下载：[打开文件](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/folder/CI0DUaoY/file/jMtnmYYY)

### Node 镜像与启动模式相关包

- `intelvisualcomputeaccelerator_persistent_reference_ubuntu_16.04.3_2.3.26.zip`
  说明：Ubuntu 持久化参考镜像，适合 BlockIO 长期保留环境。
  快捷下载：[打开文件](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/folder/CI0DUaoY/file/6N0BmIxY)
- `intelvisualcomputeaccelerator_volatile_reference_ubuntu_16.04.3_2.3.26.zip`
  说明：Ubuntu 易失性参考镜像，适合 RAMDisk 或临时测试。
  快捷下载：[打开文件](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/folder/CI0DUaoY/file/LNtzlaLB)
- `intelvisualcomputeaccelerator_persistent_reference_centos_7.4_k4.14.20_2.3.26.zip`
  说明：CentOS 持久化参考镜像。
  快捷下载：[打开文件](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/folder/CI0DUaoY/file/TBsllKjb)
- `intelvisualcomputeaccelerator_volatile_reference_centos_7.4_k4.14.20_2.3.26.zip`
  说明：CentOS 易失性参考镜像。
  快捷下载：[打开文件](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/folder/CI0DUaoY/file/SZ8RgYLa)
- `intelvisualcomputeaccelerator_persistent_production_centos_7.4_2.1.292.zip`
  说明：CentOS 持久化生产镜像，适合看官方生产化路线。
  快捷下载：[打开文件](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/folder/CI0DUaoY/file/DcsxTKRA)
- `intelvisualcomputeaccelerator_volatile_kvm_production_centos_7.4_2.2.29.zip`
  说明：面向 KVM 的易失性生产镜像。
  快捷下载：[打开文件](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/folder/CI0DUaoY/file/XAszWKTI)
- `intelvisualcomputeaccelerator_volatile_kvmgt_ubuntu_16.04.3_2.2.29.zip`
  说明：Ubuntu 路线下与 KVMGT 相关的易失性镜像。
  快捷下载：[打开文件](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/folder/CI0DUaoY/file/mRt1lSCZ)
- `intelvisualcomputeaccelerator_windows_image_creation_package_2.3.26.zip`
  说明：Windows 节点镜像制作包，是 Windows 路线最关键的入口之一。
  快捷下载：[打开文件](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/folder/CI0DUaoY/file/eQ9xzYCR)

### Windows 镜像制作与配套依赖

- `win64_15.45.5174.zip`
  说明：Intel 图形驱动压缩包，常作为 Windows 节点图形驱动依赖。
  快捷下载：[打开文件](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/folder/CI0DUaoY/file/yF9zmSRY)
- `adksetup.exe`
  说明：Windows ADK 安装程序，制作 Windows 镜像时常见依赖。
  快捷下载：[打开文件](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/folder/CI0DUaoY/file/fA0DBAYb)
- `VirtualBox-7.0.14-161095-Win.exe`
  说明：Windows 镜像制作流程里配套使用的虚拟化工具。
  快捷下载：[打开文件](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/folder/CI0DUaoY/file/zQ9jiSAb)
- `tightvnc-2.8.81-gpl-setup-64bit.msi`
  说明：制作或调试 Windows 镜像时常见的远程桌面辅助工具。
  快捷下载：[打开文件](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/folder/CI0DUaoY/file/jNsDUQpQ)
- `cn_windows_10_business_editions_version_1809_updated_sept_2019_x64_dvd_f873d037.iso`
  说明：Windows 10 企业版系安装镜像。
  快捷下载：[打开文件](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/folder/CI0DUaoY/file/WM8hFaqD)
- `cn_windows_server_2016_vl_x64_dvd_11636695.iso`
  说明：Windows Server 2016 安装镜像。
  快捷下载：[打开文件](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/folder/CI0DUaoY/file/uZ0HUKZL)
- `vca_create_windows_image.ps1`
  说明：Windows 镜像创建 PowerShell 脚本。
  快捷下载：[打开文件](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/folder/CI0DUaoY/file/3RlFSaSR)
- `vca_create_windows_image.txt`
  说明：Windows 镜像创建说明文本。
  快捷下载：[打开文件](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/folder/CI0DUaoY/file/GNsjXKzC)

### 目录型驱动与工具入口

- `GFX_driver`
  代表性文件：`Setup.exe`, `Graphics/igdlh64.inf`, `Graphics/IntelOpenCL64.dll`
  说明：Windows 图形驱动完整目录，适合直接浏览驱动安装器、INF 与 OpenCL 相关文件。
  快捷入口：[打开目录](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/folder/bVkBhayL)
- `VCA_Windows_drivers`
  代表性文件：`Vca.inf`, `Vca.sys`, `VcaBlockIo.inf`, `VcaVeth.inf`
  说明：VCA 相关 Windows 驱动目录，包含主驱动、BlockIO 与虚拟网卡驱动。
  快捷入口：[打开目录](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/folder/DFsTSSTL)
- `Xen`
  代表性文件：`xenbus.inf`, `xennet.inf`, `xenvif.inf`
  说明：Xen 总线与网络相关驱动目录。
  快捷入口：[打开目录](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/folder/HN9DkQSZ)
- `answer_files`
  代表性文件：`WIN10/AutoUnattend.xml`, `WS2016/AutoUnattend.xml`
  说明：无人值守安装应答文件目录，适合制作 Windows 镜像时配套使用。
  快捷入口：[打开目录](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/folder/OFkjBQYT)
- `VcaKmdWin`
  代表性文件：`Win8.1Release-64/Vca Package/Vca.inf`
  说明：另一套 Windows 驱动目录，适合与 `VCA_Windows_drivers` 对照查看。
  快捷入口：[打开目录](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/folder/iV8zGKiZ)
- `VCAgent`
  代表性文件：`VCAgent.exe`, `VCAgent.exe.config`
  说明：VCA Agent 相关程序目录。
  快捷入口：[打开目录](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/folder/XItBUSQJ)

### 官方 PDF 文档

- `VCA_SoftwareUserGuide.pdf`
  说明：软件使用说明书。
  快捷下载：[打开文件](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/folder/CI0DUaoY/file/XJ9h0CIR)
- `VCA2_HW_User_Guide.pdf`
  说明：硬件用户手册。
  快捷下载：[打开文件](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/folder/CI0DUaoY/file/ectlVA4J)

### 建议优先下载顺序

1. 先下载与宿主机系统对应的 `host` 包。
2. 再下载一套 `persistent_reference` 或 `volatile_reference` 镜像。
3. 如果目标包含 Windows 节点，再补 `windows_image_creation_package` 与 `vca_create_windows_image` 相关文件。
4. 根据镜像制作流程补 `GFX_driver`、`VCA_Windows_drivers`、`Xen`、`answer_files`。
5. 只有在需要做源码考证、脚本核对或内核适配时，再下载 `sources`、`kernels_development_package` 和 `build_scripts`。

## Suggested Reading Order

### 中文

首次接触 VCA2 时，可按以下顺序阅读：

1. `快速开始`
2. `VCA2 概览与硬件结构`
3. `兼容性、前置条件与准备清单`
4. `宿主机部署指南`
5. `Node 镜像、启动模式与持久化`
6. `网络、SSH 与服务部署`
7. `应用场景、风险、排错与 FAQ`

### English

For readers who are new to Intel VCA2, start with:

1. `English Quick Start`
2. `English Documentation Guide`
3. then use the Chinese detailed docs as the primary technical set

## Publishing Note

### 中文

- `docs/` 适合作为 GitHub 仓库主入口
- 如果后续继续公开更多资料，建议维持“整理文档”和“执行资料包”分层
- 老系统与过期驱动具有明显安全风险，不要让未隔离的宿主机直接暴露在公网

### English

- Use `docs/` as the main documentation surface for GitHub visitors
- Keep public documentation separate from package-specific execution details
- Do not expose an unisolated legacy host system directly to the public internet
