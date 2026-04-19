# Official Driver and Dependency Index

This page highlights the most important files inside the **official Intel VCA2 Mega package** so repository visitors can quickly find the driver packages, images, dependencies, and tooling that matter first.

All quick links below were generated from the public folder contents visible on `2026-04-19`. Descriptions are summarized from official filenames and directory layout; exact commands and workflow details should still be taken from the package itself.

## Package Overview

- Public folder: <https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw>
- Total size: `17.09 GB`
- Files: `479`
- Subfolders: `91`

## Core Host Packages

| File | Purpose | Quick Link |
| --- | --- | --- |
| `intelvisualcomputeaccelerator_host_ubuntu_16.04.3_k4.14.20_2.3.26.zip` | Official Ubuntu host-side driver and management package. | [Download](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/file/eZlRhaSR) |
| `intelvisualcomputeaccelerator_host_centos_7.4_k4.14.20_2.3.26.zip` | Official CentOS host-side driver and management package. | [Download](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/file/eA9hHQ4b) |
| `intelvisualcomputeaccelerator_host_debian_8.7_k4.14.20_2.3.26.zip` | Official Debian host-side driver and management package. | [Download](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/file/GJljSCbK) |
| `intelvisualcomputeaccelerator_kernels_development_package_2.3.26.zip` | Kernel development package for module or platform work. | [Download](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/file/XF8hiIqL) |
| `intelvisualcomputeaccelerator_build_scripts_2.3.26.zip` | Build scripts package. | [Download](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/file/fI9hlYjY) |
| `intelvisualcomputeaccelerator_sources_2.3.26.zip` | Official source package for research and verification. | [Download](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/file/2Qs1yAjC) |
| `intelvisualcomputeaccelerator_bios_2.3.26.zip` | BIOS-related firmware package. | [Download](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/file/KEtTRajQ) |
| `intelvisualcomputeaccelerator_eeprom_2.3.26.zip` | EEPROM-related maintenance package. | [Download](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/file/jMtnmYYY) |

## Node Images

| File | Purpose | Quick Link |
| --- | --- | --- |
| `intelvisualcomputeaccelerator_persistent_reference_ubuntu_16.04.3_2.3.26.zip` | Ubuntu persistent reference image for BlockIO-style use. | [Download](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/file/6N0BmIxY) |
| `intelvisualcomputeaccelerator_volatile_reference_ubuntu_16.04.3_2.3.26.zip` | Ubuntu volatile reference image for temporary or RAMDisk-style use. | [Download](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/file/LNtzlaLB) |
| `intelvisualcomputeaccelerator_persistent_reference_centos_7.4_k4.14.20_2.3.26.zip` | CentOS persistent reference image. | [Download](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/file/TBsllKjb) |
| `intelvisualcomputeaccelerator_volatile_reference_centos_7.4_k4.14.20_2.3.26.zip` | CentOS volatile reference image. | [Download](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/file/SZ8RgYLa) |
| `intelvisualcomputeaccelerator_persistent_production_centos_7.4_2.1.292.zip` | Persistent production image package. | [Download](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/file/DcsxTKRA) |
| `intelvisualcomputeaccelerator_volatile_kvm_production_centos_7.4_2.2.29.zip` | Volatile production image for KVM-related workflows. | [Download](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/file/XAszWKTI) |
| `intelvisualcomputeaccelerator_volatile_kvmgt_ubuntu_16.04.3_2.2.29.zip` | Ubuntu volatile image for KVMGT-related workflows. | [Download](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/file/mRt1lSCZ) |
| `intelvisualcomputeaccelerator_windows_image_creation_package_2.3.26.zip` | The main package for Windows node image creation. | [Download](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/file/eQ9xzYCR) |

## Windows Image Dependencies

| File or Folder | Notes | Quick Link |
| --- | --- | --- |
| `win64_15.45.5174.zip` | Intel graphics driver package used in Windows-side workflows. | [Download](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/file/yF9zmSRY) |
| `adksetup.exe` | Windows ADK installer. | [Download](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/file/fA0DBAYb) |
| `VirtualBox-7.0.14-161095-Win.exe` | VirtualBox installer used by the image-build flow. | [Download](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/file/zQ9jiSAb) |
| `tightvnc-2.8.81-gpl-setup-64bit.msi` | TightVNC installer for Windows-side setup and debugging. | [Download](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/file/jNsDUQpQ) |
| `GFX_driver` | Full graphics driver directory. Representative files: `Setup.exe`, `Graphics/igdlh64.inf`, `Graphics/IntelOpenCL64.dll`. | [Open Folder](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/folder/bVkBhayL) |
| `VCA_Windows_drivers` | Windows VCA driver directory. Representative files: `Vca.inf`, `VcaBlockIo.inf`, `VcaVeth.inf`. | [Open Folder](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/folder/DFsTSSTL) |
| `Xen` | Xen driver directory. Representative files: `xenbus.inf`, `xennet.inf`, `xenvif.inf`. | [Open Folder](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/folder/HN9DkQSZ) |
| `answer_files` | Unattended installation answer files such as `WIN10/AutoUnattend.xml` and `WS2016/AutoUnattend.xml`. | [Open Folder](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/folder/OFkjBQYT) |
| `vca_create_windows_image.ps1` | PowerShell image creation script. | [Download](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/file/3RlFSaSR) |
| `vca_create_windows_image.txt` | Text instructions for the Windows image workflow. | [Download](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/file/GNsjXKzC) |

## Official PDF Manuals

| File | Purpose | Quick Link |
| --- | --- | --- |
| `VCA_SoftwareUserGuide.pdf` | Software user guide. | [Download](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/file/XJ9h0CIR) |
| `VCA2_HW_User_Guide.pdf` | Hardware user guide. | [Download](https://mega.nz/folder/6Y9lxYzK#NIYh72gVUlZHoSayG2ebWw/file/ectlVA4J) |
