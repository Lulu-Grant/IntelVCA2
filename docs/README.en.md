# Intel VCA2 Documentation Guide

This page is the English landing guide for the repository.

The full technical documentation set is currently written in Chinese, because the original source materials and the hands-on deployment context are Chinese-first. To make the repository more accessible for English readers, this guide explains what each document covers and where to start.

## Recommended Reading Order

1. [English Quick Start](./QUICKSTART.en.md)
2. [Chinese Documentation Guide](./00-文档导航.md)
3. [VCA2 Overview and Hardware Structure](./01-VCA2概览与硬件结构.md)
4. [Compatibility and Preparation Checklist](./02-兼容性与准备清单.md)
5. [Host Deployment Guide](./03-宿主机部署指南.md)
6. [Node Images and Boot Modes](./04-Node镜像与启动模式.md)
7. [Networking, SSH, and Service Deployment](./05-网络访问与服务部署.md)
8. [Limits, Risks, and FAQ](./06-应用限制风险与FAQ.md)
9. [Documentation Scope and Boundaries](./07-文档说明与使用边界.md)

## What Each Document Covers

## `01-VCA2概览与硬件结构`

- what Intel VCA2 is
- why it is not a normal GPU
- why the three-node architecture matters

## `02-兼容性与准备清单`

- platform and motherboard compatibility
- cooling and power expectations
- why consumer boards often fail
- why VFIO / VM passthrough is usually not the right route

## `03-宿主机部署指南`

- the role of the host system
- legacy OS expectations
- hardware installation flow
- driver and node-management workflow

## `04-Node镜像与启动模式`

- RAMDisk vs BlockIO
- persistence tradeoffs
- image planning
- why BlockIO is generally preferred for long-term use

## `05-网络访问与服务部署`

- internal PCIe-based networking model
- SSH access to nodes
- service deployment mindset
- Jellyfin / media workload considerations

## `06-应用限制风险与FAQ`

- what Intel VCA2 is still good for
- what it is not good for in modern usage
- security and maintenance risks
- common troubleshooting directions

## `07-文档说明与使用边界`

- how to use this documentation correctly
- why exact commands should still come from the official package

## Important Note

This repository is a structured guide. It does **not** replace the full official driver, image, and tooling package.

The official package should remain the primary source for:

- exact installation commands
- node-management commands
- image mount commands
- service names and script paths
- credentials and version-specific behavior

## Search Terms

For search and discovery, the most relevant terms are:

`Intel VCA2`, `Intel Visual Compute Accelerator 2`, `Intel VCA2 guide`, `Intel VCA2 documentation`, `Intel VCA2 deployment`, `Intel VCA2 BlockIO`, `Intel VCA2 RAMDisk`, `Intel VCA2 transcoding`, `Intel VCA2 Jellyfin`
