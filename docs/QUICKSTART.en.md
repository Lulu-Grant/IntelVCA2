# Intel VCA2 Quick Start

This quick start is for readers who want the shortest possible path before working with the full official driver and image package.

## 1. Decide Whether Intel VCA2 Is Right for You

You are a good fit if:

- you already own Intel VCA2 or are about to buy one
- you have access to a server or workstation platform
- you accept legacy OS requirements
- you are interested in experimentation, documentation, or niche enterprise hardware

You are probably **not** a good fit if:

- you just want an easy modern transcoding card
- you want low power, low noise, and minimal maintenance
- you do not want to touch legacy Linux environments

## 2. The Four Most Important Facts

### 2.1 Platform first

Intel VCA2 usually wants:

- a server-grade or workstation-grade platform
- strong airflow
- sufficient PCIe and MMIO resources

Do not assume a normal consumer motherboard will work well.

### 2.2 Legacy OS first

The most commonly referenced working route in the collected materials is:

- **CentOS 7.6 on bare metal**

### 2.3 Official package first

Before doing anything serious, make sure you have:

- the host OS installer
- the complete official driver package
- the node image package
- the package-specific documentation

### 2.4 Expectations first

Intel VCA2 is best treated as:

- a fascinating legacy enterprise compute/video card

not as:

- a modern, convenient, efficient daily-use platform

## 3. Suggested Order of Operations

1. confirm hardware and cooling
2. install a compatible host OS
3. install the card and verify PCIe-level detection
4. install host drivers and node-management tools
5. confirm node visibility
6. prefer **BlockIO** for long-term node environments
7. set up internal networking and SSH access
8. only then move on to service deployment

## 4. Most Common Mistakes

- buying the card before gathering the package and documents
- attempting VFIO / VM passthrough first
- using weak-airflow consumer hardware
- assuming modern distributions will just work
- deploying services before understanding RAMDisk vs BlockIO

## 5. Best Practical Advice

If you want a stable long-term setup:

- keep the host focused on VCA2
- keep node roles clear
- prefer BlockIO for persistence
- document driver version, image source, and node purpose

## 6. Next Step

After this page, go to:

- [English Documentation Guide](./README.en.md)
